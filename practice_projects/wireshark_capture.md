# 🛰️ Mini Project: Ping & Packet Capture

**Project:** CacheMeIfYouCam  
**Goal:** Use `ping` and Wireshark to observe ICMP traffic in a live packet capture.

---

## 🎯 Objective

I wanted to see what actually happens when I run a simple `ping` command — and learn how to capture and examine those packets in Wireshark. This helped me understand ICMP traffic, round-trip times, and basic filtering in Wireshark.

---

## 🧰 What I Used

- Windows 11
- Wireshark (latest version)
- Command Prompt (`cmd`)
- Internet connection

---

## 🐾 Steps I Took

### 1. Open Wireshark
- I launched Wireshark and selected my **active network interface** (mine was named something like `Wi-Fi`).
- Before starting the capture, I set a **capture filter** to only collect ICMP packets:

### 2. Start Capture
- I hit the shark fin icon 🦈 to begin recording.

### 3. Ran a Ping Command
In `cmd`, I typed:
ping google.com

It sent 4 echo requests and received 4 replies.

### 4. Stopped Capture
Once the ping finished, I went back to Wireshark and clicked the red square (stop) to end the capture.

---

## 🧠 What I Observed

- Each ping request (`Echo (ping) request`) was matched by a reply (`Echo (ping) reply`).
- The **Source and Destination IPs** matched what I expected: my IP → Google's.
- Under `ICMP`, I saw sequence numbers and TTL values.
- I used the **"Statistics" → "Summary"** and **"Conversation List"** to dig deeper.

---

## ⏱️ Round Trip Time (RTT)
- I looked at the `Delta time` and also hovered over each ICMP packet to get the RTT.
- Wireshark didn’t always show exact RTTs, but I could estimate them by checking the time differences between request/reply pairs.

---## Round-Trip Time (RTT) Example

During my packet capture, I observed the following ICMP packets:

| Packet No. | Time (s)   | Source IP        | Destination IP   | Description             |
|------------|------------|------------------|------------------|-------------------------|
| 18         | 7.323950   | 172.21.234.216   | 165.20.53.161    | Echo (ping) request      |
| 19         | 7.331671   | 165.20.53.161    | 172.21.234.216   | Echo (ping) reply        |

To calculate the round-trip time (RTT), I subtracted the time of the request packet from the time of the reply packet:
RTT = 7.331671 s - 7.323950 s = 0.007721 seconds ≈ 7.7 milliseconds

This RTT represents the time it took for the ping request to reach the destination and for the reply to return to my machine.

Understanding RTT helps me gauge the latency or delay between two points on a network, which is crucial for diagnosing network performance.

### Latency Interpretation

The round-trip time (RTT) of approximately 7.7 milliseconds indicates that the network connection between my computer and the destination server is very fast and responsive. Generally, an RTT below 20 ms is considered excellent, suggesting that the data packets traveled with minimal delay. This low latency likely means the server is geographically close or that the network path is clear and efficient. For context, latencies under 20 ms are ideal for most applications, while higher values might cause delays in activities like gaming or video calls. This experience reassures me that the connection I tested is healthy and efficient.


## 🔒 Anonymizing the Capture

I made sure not to upload any sensitive files directly. If I decide to upload `.pcapng`, I’ll either:
- Use tools like `TraceWrangler` or Wireshark’s redaction features
- Or edit out visible IPs/MACs before sharing

---

## 💾 Should You Upload the PCAP?

If it’s anonymized: yes, that’s a great way to share what you observed.  
If not: just include screenshots or write up your findings instead.

---

## 📌 Lessons Learned

- ICMP is dead simple to track.
- Even a basic ping gives me something meaningful to analyze.
- Packet capture tools like Wireshark are powerful — and surprisingly visual!

---

*First packet, first project. One small ping for me, one giant leap toward packet mastery.* 😎
