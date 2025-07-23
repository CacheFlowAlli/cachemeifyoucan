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

---

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
