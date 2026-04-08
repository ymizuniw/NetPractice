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
- Amazon Web Services (AWS) — What Is the OSI Model?:
  - https://aws.amazon.com/what-is/osi-model/
- @musenmai "SSL/TLSのハンドシェイクを14ステップで確認する" (2025)
  - https://qiita.com/musenmai/items/43929eb9f6f31908fd51

---

## Briefings

### OSI Reference Model

| Layer | Name | Examples | Description |
|-------|------|----------|-------------|
| 1 | **Physical Layer** | Fiber-optic cables, copper cabling, Bluetooth | Transmits raw bit streams over physical media. |
| 2 | **Data Link Layer** | Ethernet, MAC | Manages ethernet frames using MAC address. (Port numbers belong to the Transport Layer.) |
| 3 | **Network Layer** | Routers, IP | Uses IP as the logical address of nodes possibly beyond the local network, while MAC is physical identification of each node in the same network. |
| 4 | **Transport Layer** | TCP, UDP | TCP ensures complete packet transmission, retransmitting and reassembling packets in the correct order if errors are detected. UDP does not check for completeness and does not retransmit or reassemble. |
| 5 | **Session Layer** | TLS, SSL | Encrypts the correspondence between client and server. |
| 6 | **Presentation Layer** | JSON, HTML | Manages the format and structure of the contents of the transmission. |
| 7 | **Application Layer** | EC sites, Blogs | The front end of client-server correspondence. Users access Application Layer functions and receive services from it. |

---

### IP Addressing

Allocates an IP to each device to identify the logical location of the device (node).

### Subnet Masks

Subnet masks are used to divide one network into several smaller networks. This improves transmission efficiency by limiting the broadcast domain.

### Default Gateways

If the packet destination is outside the local network, the packet is transmitted to the default gateway, which forwards it to the external network through another interface.

### Switches

Switches improve the efficiency of broadcasting by holding the source MAC address combined with the incoming port. The switch first looks up its MAC address table, and if no match is found, broadcasts the packet.

---

## Level Requirements

### Level 1
Two local networks exist. Check that the subnet mask and IP correspond correctly for each network.

### Level 2
Two local networks exist. Check that the subnet mask and IP correspond correctly for each network. Note that the `/30` notation for writing masks is introduced here.

### Level 3
One network consisting of three hosts connected via **Switch_1**. All hosts share the same network address.

### Level 4
One network consisting of **Gateway R1** and two hosts connected via **Switch_1**. Note that the three gateway IPs and masks are similar and must be carefully distinguished from one another.

### Level 5
Two different networks branching from **Router R**. Each host (Host A, Host B) is routed to its respective network via the routing table — a new device introduced at this level.

### Level 6
One local network connected through **interface R1** of a gateway, with the Internet connected via **interface R2**. Focus on the routing table and how it aligns with packet flow. The key new concept is forwarding by a gateway between a local network and an external network (Internet).

### Level 7
A local network with two routers connecting two hosts. Pay attention to the direction of routing — it is used to connect two router interfaces to each other.

### Level 8
The Internet router has the following routing table entry:
- `157.89.189.0/26` → `163.246.250.12`

The local network must be divided into three subnets within 6 bits.

### Level 9
Multiple networks composed of **two routers**, **four hosts**, and the **Internet**, segmented into three distinct networks. The Internet routing table has three slots in total. Additionally, **R1** has two separate slots for **R2**, meaning the two network addresses from R2 can be chosen freely by the network manager.

### Level 10
Multiple networks composed of **two routers**, **four hosts**, and the **Internet**.
- A single route from the Internet to the external gateway of **R1** restricts addressing to `128.142.168.0/24`.
- **R11** has a last octet of `1` and a mask of `128` (`/1` in binary: `10000000`), so the network address satisfies `address & 10000000 = 00000000`. The interfaces **R13**, **R23**, and **R22** must have addresses whose last octet begins with `1` (i.e., `1xxxxxxx`).
