# 3-Router OSPF Lab (Cisco Packet Tracer)

This project demonstrates **dynamic routing using OSPF** across 3 routers in a triangle topology.  
Each router connects to a LAN with PCs, and OSPF is configured to allow full end-to-end communication.  

---

## 📌 Topology Overview

```

\[PC1]---\[R1]---\[R2]---\[PC2]
\     /
\   /
\[R3]
|
\[PC3]

````

- **R1 LAN:** 192.168.1.0/24  
- **R2 LAN:** 192.168.2.0/24  
- **R3 LAN:** 192.168.3.0/24  
- **Router links:**  
  - R1–R2: 10.0.12.0/30  
  - R2–R3: 10.0.23.0/30  
  - R3–R1: 10.0.31.0/30  

---

## Device Configuration

### R1 Configuration

```bash
enable
conf t
hostname R1

# Interfaces
int g0/0
 ip address 192.168.1.1 255.255.255.0
 no shut

int s0/0/0
 ip address 10.0.12.1 255.255.255.252
 no shut

int s0/0/1
 ip address 10.0.31.1 255.255.255.252
 no shut

# OSPF
router ospf 1
 network 192.168.1.0 0.0.0.255 area 0
 network 10.0.12.0 0.0.0.3 area 0
 network 10.0.31.0 0.0.0.3 area 0
````

---

### R2 Configuration

```bash
enable
conf t
hostname R2

# Interfaces
int g0/0
 ip address 192.168.2.1 255.255.255.0
 no shut

int s0/0/0
 ip address 10.0.12.2 255.255.255.252
 no shut

int s0/0/1
 ip address 10.0.23.1 255.255.255.252
 no shut

# OSPF
router ospf 1
 network 192.168.2.0 0.0.0.255 area 0
 network 10.0.12.0 0.0.0.3 area 0
 network 10.0.23.0 0.0.0.3 area 0
```

---

### R3 Configuration

```bash
enable
conf t
hostname R3

# Interfaces
int g0/0
 ip address 192.168.3.1 255.255.255.0
 no shut

int s0/0/0
 ip address 10.0.23.2 255.255.255.252
 no shut

int s0/0/1
 ip address 10.0.31.2 255.255.255.252
 no shut

# OSPF
router ospf 1
 network 192.168.3.0 0.0.0.255 area 0
 network 10.0.23.0 0.0.0.3 area 0
 network 10.0.31.0 0.0.0.3 area 0
```

---

## ✅ Verification Steps

1. Assign IP addresses to **PC1, PC2, PC3**:

   * PC1 → 192.168.1.10 /24 (Gateway: 192.168.1.1)
   * PC2 → 192.168.2.10 /24 (Gateway: 192.168.2.1)
   * PC3 → 192.168.3.10 /24 (Gateway: 192.168.3.1)

2. Verify OSPF neighbors:

   ```bash
   R1# show ip ospf neighbor
   R2# show ip ospf neighbor
   R3# show ip ospf neighbor
   ```

3. Test end-to-end connectivity:

   * From PC1, ping PC2 and PC3.
   * From PC2, ping PC1 and PC3.
   * From PC3, ping PC1 and PC2.

All pings should succeed ✅

---

## 🚀 How to Use

1. Open the `.pkt` file in Cisco Packet Tracer.
2. Follow configurations above if devices are not preconfigured.
3. Run ping tests between PCs.

---