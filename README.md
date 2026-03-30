# 🌐 Cisco Networking Command Cheat Sheet

A quick reference for commonly used **Cisco Router and Switch commands**.
Useful for **CCNA students, networking beginners, and network engineers**.

---

# 📑 Table of Contents

* Basic Switch Configuration
* Console & Remote Access
* Password Encryption
* Banner Configuration
* Switch Management IP
* Save Configuration
* SSH Configuration
* Command Aliases
* Verification Commands
* Port Security
* VLAN Configuration
* Trunk Configuration
* Router Basic Configuration
* Interface Configuration
* Static Routing
* RIP Configuration
* OSPF Configuration

---

# ⚙️ Basic Switch Configuration

### Change Hostname

```bash
Switch(config)# hostname SW1
```

### Configure Enable Password

```bash
SW1(config)# enable secret cisco
SW1(config)# enable password notcisco
```

---

# 🔐 Console Access Security

```bash
SW1(config)# line console 0
SW1(config-line)# password cisco
SW1(config-line)# login
```

---

# 🌍 Remote Access (VTY)

```bash
SW1(config)# line vty 0 4
SW1(config-line)# password cisco
SW1(config-line)# login
```

---

# 🔒 Encrypt Passwords

```bash
SW1(config)# service password-encryption
```

---

# 📢 Banner Message

```bash
SW1(config)# banner motd $

UNAUTHORIZED ACCESS IS PROHIBITED

$
```

---

# 🌐 Switch Management IP

```bash
SW1(config)# interface vlan 1
SW1(config-if)# ip address 172.16.1.11 255.255.255.0
SW1(config-if)# no shutdown
```

### Default Gateway

```bash
SW1(config)# ip default-gateway 172.16.1.1
```

---

# 💾 Save Configuration

```bash
SW1# copy running-config startup-config
```

or

```bash
SW1# write memory
```

---

# 🧰 Useful Environment Commands

Disable DNS lookup

```bash
SW1(config)# no ip domain-lookup
```

Command history

```bash
SW1(config)# line vty 0 4
SW1(config-line)# history size 15
```

Session timeout

```bash
SW1(config-line)# exec-timeout 10 30
```

Logging synchronous

```bash
SW1(config-line)# logging synchronous
```

---

# 🔑 SSH Configuration

### Set Domain Name

```bash
SW1(config)# ip domain-name example.com
```

### Create Local User

```bash
SW1(config)# username admin password cisco
```

### Generate RSA Key

```bash
SW1(config)# crypto key generate rsa
```

Key size example

```
1024
```

### Enable SSH Version 2

```bash
SW1(config)# ip ssh version 2
```

### Enable SSH on VTY Lines

```bash
SW1(config)# line vty 0 4
SW1(config-line)# login local
SW1(config-line)# transport input telnet ssh
```

---

# ⚡ Command Aliases

```bash
SW1(config)# alias exec c configure terminal
SW1(config)# alias exec s show ip interface brief
SW1(config)# alias exec sr show running-config
```

---

# 🔍 Verification Commands

```bash
show version
show running-config
show startup-config
show history
show ip interface brief
show interfaces description
show interfaces status
```

---

# 🔐 Port Security

```bash
SW1(config)# interface fastEthernet 0/5
SW1(config-if)# switchport mode access
SW1(config-if)# switchport port-security
SW1(config-if)# switchport port-security maximum 1
SW1(config-if)# switchport port-security violation shutdown
SW1(config-if)# switchport port-security mac-address sticky
```

---

# 🏷 VLAN Configuration

### Create VLAN

```bash
SW1(config)# vlan 10
SW1(config-vlan)# name SALES
```

### Assign VLAN to Interface

```bash
SW1(config)# interface fastEthernet 0/5
SW1(config-if)# switchport mode access
SW1(config-if)# switchport access vlan 10
```

---

# 🔗 Trunk Configuration

```bash
SW1(config)# interface fastEthernet 0/1
SW1(config-if)# switchport mode trunk
SW1(config-if)# switchport trunk allowed vlan add 10
```

---

# 🖧 Router Basic Configuration

```bash
Router(config)# hostname R1
R1(config)# enable secret cisco
R1(config)# line console 0
R1(config-line)# password cisco
R1(config-line)# login
```

---

# 🌐 Router Interface Configuration

```bash
R1(config)# interface fastEthernet 0/0
R1(config-if)# ip address 172.16.1.1 255.255.255.0
R1(config-if)# no shutdown
```

---

# 🛣 Static Routing

```bash
R1(config)# ip route 10.1.2.0 255.255.255.0 10.1.128.1
```

### Default Route

```bash
R1(config)# ip route 0.0.0.0 0.0.0.0 199.1.1.1
```

---

# 🔁 RIP Configuration

```bash
R1(config)# router rip
R1(config-router)# version 2
R1(config-router)# network 10.0.0.0
R1(config-router)# no auto-summary
```

---

# 🌍 OSPF Configuration

```bash
R1(config)# router ospf 10
R1(config-router)# network 10.0.0.0 0.255.255.255 area 0
```

### Set Router ID

```bash
R1(config-router)# router-id 1.1.1.1
```

---

# ⭐ Purpose

This cheat sheet is created to help:

* CCNA students
* Networking beginners
* Network engineers practicing Cisco labs
* Packet Tracer learners

---

# 🤝 Contributing

Contributions are welcome.

You can:

* Add more Cisco commands
* Add troubleshooting commands
* Improve explanations

Submit a **pull request**.

---

# 📚 License

Educational use for **network learning and lab practice**.
