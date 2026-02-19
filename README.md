
# **Task 5: Capture and Analyze Network Traffic Using Wireshark**

---

## . Objective

To capture live network traffic using Wireshark, analyze different network protocols, and understand how data packets travel across a network.

---

## . Tool Used

* Wireshark (Network Protocol Analyzer)
* Operating System: Windows / Linux
* Active Interface: Wi-Fi

---



 Step 1: Install Wireshark
🔹 Windows:

Official website se download karo:
👉 https://www.wireshark.org

Install normally (Npcap install karna mandatory hai).

🔹 Linux (Ubuntu) or kali linux:
```bash
sudo apt update
sudo apt install wireshark
```

![wireshark](screenshots/wireshark-opening.png)

---

## Step 2: Select Network Interface

* Opened Wireshark.
* Selected active network interface (Wi-Fi/Ethernet) in my case i select etho0.
* now wireshark Started packet capturing.



---

## Step 3: Generate Network Traffic

* Opened a web browser and visited google.com.
* Used ping command to generate ICMP traffic:

# Visiting a website http://testphp.vulnweb.com ( it's a intenstionaly insecure site used for practice and learning purpose) for generating http trafic
# send echo request using ping
```bash
ping google.com
```
![ping](screenshots/ping.png)

# send dns queries using dig tools
qurie for A (ip adress) record of google.com
```bash
dig A google.com
```
![ping](screenshots/a-record.png)

querie for MX (mail server) record of google.com
```bash
dig mx google.com
```
![ping](screenshots/mx-record.png)



---

## Step 4: Stop Capture

* Stopped packet capture after generating trafic.

📸 **Screenshot 5 Required:**
👉 *Captured packets visible after stopping capture.*

---

## Step 5: Apply Protocol Filters

Applied the following filters in the filter bar:

* `dns`
  ![ping](screenshots/dns.png)

* `http`
  ![ping](screenshots/http.png)

  we clearly see a plain text password which i entered 

* `icmp`
  ![ping](screenshots/icmp.png)


icmp traffic:


---



## Step 7: Export Capture File

* Clicked:

  ```
  File → Save As
  ```
* Saved file as:

  ```
  network_capture.pcapng
  ```

![ping](screenshots/traffic.png)


---

# 4. Protocols Identified

### 1. DNS

* Used for domain name resolution.
* Observed query and response packets.
* Uses UDP port 53.

### 2. TCP

* Observed 3-way handshake:

  * SYN
  * SYN-ACK
  * ACK
* Provides reliable communication.

### 3. HTTPS

* Encrypted web traffic.
* Observed communication over port 443.

### 4. ICMP

* Echo Request and Echo Reply observed.
* Used to test connectivity.

---

# 5. Findings

* DNS requests occur before establishing web connections.
* TCP handshake confirms session establishment.
* HTTPS encrypts communication between client and server.
* ICMP verifies network connectivity.

---

# 6. Conclusion

The experiment successfully demonstrated live packet capture and protocol analysis using Wireshark. Multiple protocols such as DNS, TCP, HTTPS, and ICMP were identified and analyzed. The task improved understanding of how real-time network communication works at the packet level.



