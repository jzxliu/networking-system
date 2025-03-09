
```md
# Network Stack - Ethernet & ARP Implementation

## 🛠️ Project Overview
This project implements a **simplified network interface** that handles:
- Sending and receiving **Ethernet frames**.
- Processing **ARP requests & replies**.
- Managing an **ARP cache** for efficient address resolution.
- Handling **queued packets** waiting for ARP resolution.

This is part of an educational assignment for **CSC458 (Computer Networking)**.

---

## 📂 Project Structure
```
📦 project_root/
 ┣ 📜 CMakeLists.txt  # Build configuration
 ┣ 📂 src/
 ┃ ┣ 📜 network_interface.hh  # Header file for NetworkInterface class
 ┃ ┣ 📜 network_interface.cc  # Implementation of NetworkInterface class
 ┃ ┣ 📜 ethernet_frame.hh  # Ethernet frame structure
 ┃ ┣ 📜 arp_message.hh  # ARP message structure
 ┃ ┣ 📜 ipv4_datagram.hh  # IPv4 packet structure
 ┃ ┣ 📜 address.hh  # IP address utilities
 ┣ 📂 tests/
 ┃ ┣ 📜 net_interface_test_pending.cc  # Test cases for pending packets
 ┣ 📜 README.md  # Project documentation
```

---

## 🚀 Features
- **Ethernet Frame Handling** 🖧  
  - Wraps IP packets inside **Ethernet frames** and sends them.
  - Extracts **IPv4 payloads** from incoming frames.

- **ARP Protocol Implementation** 🔍  
  - Resolves **MAC addresses from IPs** via ARP requests.
  - Maintains an **ARP cache** (with a 30-second expiration).
  - Responds to **incoming ARP requests** for this device.

- **Packet Queuing for ARP Resolution** ⏳  
  - Stores packets waiting for ARP responses.
  - Retransmits pending packets when a response arrives.

---

## ⚙️ Installation & Setup
### **1️⃣ Clone the Repository**
```bash
git clone https://github.com/your-username/network-interface.git
cd network-interface
```

### **2️⃣ Build the Project**
Ensure you have `CMake` and `g++` installed:
```bash
mkdir build
cd build
cmake ..
cmake --build .
```

### **3️⃣ Run Tests**
```bash
cd build
ctest --verbose
```
Or, run a specific test:
```bash
./build/pa1
```

---

## 🐞 Debugging
If you encounter **segmentation faults**, use `gdb`:
```bash
gdb --args ./build/pa1
```
Inside `gdb`, type:
```gdb
run
backtrace
```
To check memory issues, use `valgrind`:
```bash
valgrind --leak-check=full --show-leak-kinds=all ./build/pa1
```

---

## 📌 Known Issues
- **Packet Loss in Edge Cases** 🚨  
  - Packets might still drop if **an ARP reply arrives right before expiry**.
- **Segmentation Faults in Certain Tests** ⚠️  
  - Debugging `net_interface_test_pending.cc` to resolve crashes.

---

## 📚 References
- **Computer Networking: A Top-Down Approach** 📖
- **RFC 826** - Address Resolution Protocol (ARP)

---

## 👨‍💻 Contributors
- **Your Name (@your-github-username)**  
- **Professor / Course Team (CSC458 - University Name)**

---

## 📝 License
This project is for educational purposes and follows the university's academic integrity policies.
```
