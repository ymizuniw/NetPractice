*This project has been created as part of the 42 curriculum by ymizuniw.*

## Overview

The goal of this project is to understand IP addressing, including subnet calculation, routing, gateways, and more. Learners use the NetPractice interface to simulate network routing.

---

## Getting Started

1. Open **Chrome** on your device.
2. Run `./net_practice/run.sh` from the repository root, then click **"net_practice"** in the browser index that opens.
3. Log in to the **Training** or **Evaluation** interface depending on your purpose.
4. After completing each configuration, click **"Get my config"** to save it locally.
5. Confirm that all **10 level configuration files** are present at the repository root — this is a submission requirement.

---

## Resources

Basic concepts of TCP/IP addressing, subnet masks, default gateways, routers, switches, and OSI layers were sourced from:

- みやたひろし, 『図解入門TCP/IP: 仕組み・動作が見てわかる』 (2020)
- Cisco Networking Academy — *Networking Basics*:
  - https://www.netacad.com/courses/networking-basics?courseLang=en-US

---

## Level Requirements

### Level 1
Two local networks exist, each with corresponding IP and network addresses.

### Level 2
Two local networks exist, each with corresponding IP and network addresses.

### Level 3
One network consisting of three hosts connected via **Switch_1**. All hosts share the same network address.

### Level 4
One network consisting of **Gateway R1** and two hosts connected via **Switch_1**. Note that the three gateway IPs and masks are similar and must be carefully distinguished from one another.

### Level 5
Two different networks branching from **Router R**. Each host (Host A, Host B) is routed to its respective network via the routing table.

### Level 6
One local network connected through **interface R1** of a gateway, with the Internet connected via **interface R2**. Focus on the routing table and how it aligns with packet flow.

### Level 7
A local network with two routers connecting two hosts.

### Level 8
- The destination network address on **Internet 1** is restricted to `157.89.189.0/26`.
- Interfaces **R21**, **R22**, and **R23** share the same network address.
- Three networks around **Router R2** are differentiated using a `/28` mask, dividing the last octet as follows:

  | Bits (last octet) | Range   |
  |-------------------|---------|
  | `0011`            | 48 – 63 |
  | `0010`            | 32 – 47 |
  | `0001`            | 17 – 31 |

### Level 9
Multiple networks composed of **two routers**, **four hosts**, and the **Internet**, segmented into three distinct networks.

### Level 10
Multiple networks composed of **two routers**, **four hosts**, and the **Internet**.
- A single route from the Internet to the external gateway of **R1** restricts addressing to `128.142.168.0/24`.
- Within the **R2** network, addresses are further divided using `/26` and `/28` masks to avoid duplication across the four local networks.