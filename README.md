# Network Stack - Ethernet & ARP Implementation

## 🦜 Project Overview
This project implements a **simplified network interface** that handles:
- Sending and receiving **Ethernet frames**.
- Processing **ARP requests & replies**.
- Managing an **ARP cache** for efficient address resolution.
- Handling **queued packets** waiting for ARP resolution.

This is part of an educational assignment for **CSC458 (Computer Networking)**.

---

## 📂 Project Structure
```
📺 project_root/
 ┓ 📄 CMakeLists.txt  # Build configuration
 ┓ 📂 src/
 ┗ ┓ 📄 network_interface.hh  # Header file for NetworkInterface class
   ┗ 📄 network_interface.cc  # Implementation of NetworkInterface class
   ┗ 📄 ethernet_frame.hh  # Ethernet frame structure
   ┗ 📄 arp_message.hh  # ARP message structure
   ┗ 📄 ipv4_datagram.hh  # IPv4 packet structure
   ┗ 📄 address.hh  # IP address utilities
 ┓ 📂 tests/
 ┗ ┓ 📄 net_interface_test_pending.cc  # Test cases for pending packets
 ┓ 📄 README.md  # Project documentation
```

---

## 🚀 Features
- **Ethernet Frame Handling** 🔧  
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

## 📚 References
- **Computer Networking: A Top-Down Approach** 📚
- **RFC 826** - Address Resolution Protocol (ARP)

---
## 📝 License
This project is for educational purposes and follows the university's academic integrity policies.
```
