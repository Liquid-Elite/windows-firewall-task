# 🔥 Windows Firewall Configuration Task

## 🎯 Objective

The goal of this lab task is to demonstrate basic firewall management skills by configuring, testing, and documenting Windows Firewall rules to filter specific network traffic.

---

## 🧰 Tools Used

- Windows 10/11 OS
- Windows Defender Firewall with Advanced Security (`wf.msc`)
- Telnet Client (`telnet`)
- (Optional) OpenSSH Server

---

## 📋 Task Steps & Actions Performed

### ✅ 1. Open Windows Firewall

- Accessed via `Win + R` → Typed `wf.msc` → Opened **Windows Defender Firewall with Advanced Security**.

---

### ✅ 2. List Current Rules

- Viewed and examined existing **Inbound** and **Outbound** rules.
- Noted default settings and filtering actions.

📸 *Screenshot included:* `screenshots/firewall-rules-list.png`

---

### ✅ 3. Block Inbound Traffic on Port 23 (Telnet)

- Created a new **Inbound Rule**:
  - Rule Type: `Port`
  - Protocol: `TCP`
  - Port: `23`
  - Action: `Block the connection`
  - Profile: All selected (Domain, Private, Public)
  - Name: `Block Telnet Port 23`


---

### ✅ 4. Test Rule by Connecting to Port 23

- Enabled Telnet Client via CMD:
  ```bash
  dism /online /Enable-Feature /FeatureName:TelnetClient
Attempted connection:

bash
Copy
Edit
telnet 127.0.0.1 23
Result: Connection failed as expected due to firewall rule.
5. Allow SSH (Port 22) Rule
Created another Inbound Rule to allow TCP traffic on Port 22 for secure SSH access.

This ensures the firewall doesn’t block legitimate secure access (e.g., via OpenSSH).


✅ 6. Remove Block Rule to Restore Original State
Deleted the previously created Block Telnet Port 23 rule to return to the system's default configuration.

📑 Interview Questions & Answers
Stored in the file: firewall_interview_questions.txt

Covers:

What is a firewall?

Stateful vs. Stateless

Inbound vs. Outbound rules

UFW vs. manual control

Why block Telnet

Common mistakes

How firewalls protect networks

What is NAT

📘 Summary: How Firewalls Filter Traffic
A firewall filters traffic by inspecting packets based on IP addresses, protocols (TCP/UDP), and port numbers. It allows or blocks traffic according to user-defined rules, helping to protect systems from unauthorized access, malware, and network-based attacks.

Inbound Rules restrict what can come into your system.

Outbound Rules control what your system can send out.

Firewalls act as gatekeepers between trusted and untrusted networks.
