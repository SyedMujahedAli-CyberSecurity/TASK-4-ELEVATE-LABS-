
# Task 4 — Setup and Use a Firewall on Windows

**Student:** Syed Mujahed Ali  
**Project:** Task 4 — Setup and Use a Firewall on Windows  

**Tools:** Windows 10/11, Windows Defender Firewall with Advanced Security, Command Prompt / PowerShell, Telnet Client

---

## Objective
Configure and test basic firewall rules on Windows to block and then remove a rule for a specific port (Telnet — TCP 23). Demonstrate understanding of inbound/outbound rules and how a firewall filters traffic.

---

## Activities and Implementation

### 1. Open Firewall Configuration Tool
Opened **Windows Defender Firewall with Advanced Security** by pressing `Win + R`, typing `wf.msc`, and pressing **Enter**.  


### 2. List Current Firewall Rules
Navigated to **Inbound Rules** and **Outbound Rules** to review existing rules and note commonly allowed services.  


### 3. Add a Rule to Block Inbound Traffic on Port 23 (Telnet)
Created a new inbound rule to block TCP port 23:
1. In **Inbound Rules**, clicked **New Rule**.
2. Selected **Port** → **Next**.
3. Chose **TCP** and entered **23** in *Specific local ports* → **Next**.
4. Selected **Block the connection** → **Next**.
5. Applied to **Domain**, **Private**, and **Public** profiles → **Next**.
6. Named the rule `Block Telnet Port 23` → **Finish**.  


### 4. Test the Block Rule
Verified the block by attempting to connect via Telnet:
- Enabled Telnet Client (Control Panel → Programs → Turn Windows features on or off → Telnet Client).
- Command Prompt test:
```cmd
telnet localhost 23
Expected result: Connection failed.

###5. (Skipped) Add Rule to Allow SSH (Port 22)
This step was skipped since SSH is not typically used on Windows. On Windows, a similar step could involve allowing RDP (TCP 3389) using the same process but selecting Allow the connection.

###6. Remove the Test Block Rule
Removed the test rule to restore the firewall to its original state by right-clicking Block Telnet Port 23 → Delete.

###7. Documented GUI Steps / Commands Used
GUI Steps:

Opened wf.msc.

Checked inbound and outbound rules.

Created a port-specific inbound rule to block TCP port 23.

Tested block using Telnet : telnet localhost 23

Deleted the test rule.

###8. How the Firewall Filters Traffic
A firewall enforces rules to allow or deny network traffic. Each incoming or outgoing connection is checked against these rules. If the traffic matches an allow rule, it is permitted; if it matches a block rule, it is denied. Rules can be based on port, protocol, IP address, application, and network profile.
