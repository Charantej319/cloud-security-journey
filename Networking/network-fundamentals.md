
# Networking Fundamentals

## 1. Introduction to Networking

A computer network is a group of devices connected to each other to share information and resources. These devices communicate using different networking protocols.

Networking is important in cloud security because cloud services, servers, applications and users communicate over networks.

## 2. Types of Networks

| Type | Description |
|---|---|
| LAN | Local Area Network, usually within a building or campus. |
| WAN | Wide Area Network, connects networks across large geographical areas. |
| MAN | Metropolitan Area Network, covers a city or large town. |
| WLAN | Wireless Local Area Network, connects devices wirelessly. |

## 3. IP Address

An IP address is a logical address assigned to a network interface. It helps devices communicate with each other over a network.

There are two main versions:

- IPv4: Uses 32-bit addressing.
- IPv6: Uses 128-bit addressing.

Examples:

- IPv4: `192.168.1.10`
- IPv6: `2001:db8::1`

### Public and Private IP Addresses

Private IP addresses are used inside local networks and are not directly routable over the public internet.

The private IPv4 ranges are:

- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

Public IP addresses are globally routable addresses used for communication over the internet.

## 4. MAC Address

A MAC (Media Access Control) address is a link-layer address associated with a network interface.

Example:

`00:0c:29:4d:ad:aa`

It is generally used to identify devices during communication within a local network.

## 5. Networking Devices

| Device | Purpose |
|---|---|
| Router | Connects different networks and forwards packets. |
| Switch | Connects multiple devices within a LAN. |
| Modem | Connects a network to an ISP's access infrastructure. |
| Firewall | Monitors and controls network traffic based on security rules. |

## 6. DNS (Domain Name System)

DNS translates domain names into IP addresses.

For example, when we enter `google.com` in a browser, DNS helps find the IP address associated with that domain.

DNS commonly uses port 53.

I tested DNS resolution in Kali Linux using:

```bash
nslookup google.com
```

The query successfully returned multiple IPv4 and IPv6 addresses.

## 7. Default Gateway

A default gateway is the device that forwards traffic from a local network to other networks when there is no more specific routing rule.

I checked my default gateway using:

```bash
ip route
```

My Kali VM showed `192.168.25.2` as its default gateway.

## 8. Basic Networking Commands in Linux

During practical work in Kali Linux, I used the following commands:

| Command | Purpose |
|---|---|
| `ip addr` | Displays IP addresses and interfaces. |
| `ip link show` | Displays network interfaces. |
| `ip route` | Displays the routing table. |
| `ip -br addr` | Displays network information in a compact format. |
| `ping` | Tests network connectivity. |
| `nslookup` | Checks DNS resolution. |
| `hostname` | Displays the system hostname. |
| `hostnamectl` | Displays system and hostname information. |
| `cat /etc/resolv.conf` | Displays DNS resolver configuration. |

## 9. Practical Work – Kali Linux

I used Kali Linux running inside VMware to explore network configuration and test connectivity.

### Network Configuration

| Property | Value |
|---|---|
| Operating System | Kali Linux |
| Virtualization | VMware |
| Network Interface | eth0 |
| IPv4 Address | 192.168.25.129 |
| Subnet Prefix | /24 |
| MAC Address | 00:0c:29:4d:ad:aa |
| Default Gateway | 192.168.25.2 |
| DNS Server | 192.168.25.2 |
| IPv6 | Link-local address available |

### Connectivity Testing

I performed two connectivity tests:

**1. Testing connectivity using an IP address**

```bash
ping -c 4 8.8.8.8
```

Result: All four packets were received with 0% packet loss.

**2. Testing connectivity using a domain name**

```bash
ping -c 4 google.com
```

Result: DNS resolution was successful, and all four packets were received.

I also used `nslookup google.com` to check DNS resolution separately.

### What I Understood

- How to identify the IP and MAC addresses of a network interface.
- How to find the default gateway.
- How DNS resolves domain names.
- How to check network connectivity using ping.
- How to inspect network interfaces and routing information in Linux.

## 10. Key Takeaways

Networking is one of the basic requirements for working in cloud security. Understanding IP addressing, DNS, routing and network interfaces will help me when learning cloud networking, firewalls, security groups and network monitoring.

This was my first practical introduction to networking using Kali Linux.
