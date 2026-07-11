# 5-wireshark

Task 5: Wireshark ICMP Capture

Objective

The objective of this task is to capture and analyze ICMP (Internet Control Message Protocol) Echo Request and Echo Reply packets using Wireshark. Three separate packet captures were created for:

1. Google (google.com)
2. Default Gateway (10.0.2.1)
3. Localhost (127.0.0.1)

Each capture contains exactly:

1. 4 ICMP Echo Requests
2. 4 ICMP Echo Replies

Environment

Operating System: Kali Linux

Packet Analyzer: Wireshark

Network Interface (Internet): eth0

Loopback Interface: lo

Network Information

Local IP Address: 10.0.2.15

Gateway IP Address: 10.0.2.1

Localhost Address: 127.0.0.1

Commands Used

Find the Default Gateway

```bash
ip route
```

Output:

default via 10.0.2.1 dev eth0

Ping Google (IPv4)

```bash
ping -4 -c 4 google.com
```

Ping Gateway

```bash
ping -c 4 10.0.2.1
```

Ping Localhost

```bash
ping -c 4 127.0.0.1
```

Wireshark Capture Procedure

1. Open Wireshark.

2. Select the appropriate interface.

   eth0 for Google and Gateway.

   lo for Localhost.

3. Apply the capture filter:

Capture Filter: icmp

4. Start the capture.

5. Execute the corresponding ping command.

6. Stop the capture after four replies.

7. Verify that the capture contains:

   4 Echo Requests

   4 Echo Replies

8. Save the capture.

Capture Files

google.pcapng

ICMP capture of Google ping.

gateway.pcapng

ICMP capture of the default gateway.

localhost.pcapng

ICMP capture of localhost.

Packet Analysis

Google Capture

Destination resolved using DNS before the ICMP packets were sent.

Four Echo Requests were transmitted.

Four Echo Replies were received successfully.

Communication occurred over the eth0 interface.

Gateway Capture

ICMP packets were exchanged directly with the default gateway.

All four requests received successful replies.

Lowest network latency among external devices.

Localhost Capture

Packets were exchanged through the loopback (lo) interface.

Traffic never left the local machine.

All requests were answered immediately.

Observations

1. All three targets successfully responded to ICMP Echo Requests.

2. Localhost (127.0.0.1) had the fastest response because communication remained within the operating system.

3. The gateway (10.0.2.1) responded with very low latency since it is directly connected on the local network.

4. Google (google.com) showed comparatively higher latency because packets traversed the internet.

5. Using the Wireshark capture filter "icmp" ensured that each capture contained only the required ICMP packets.

Conclusion

This task demonstrated how to:

1. Capture network traffic using Wireshark.

2. Apply capture filters to isolate ICMP traffic.

3. Generate ICMP packets using the ping utility.

4. Identify Echo Request and Echo Reply packets.

5. Compare communication with remote hosts, the default gateway, and the localhost interface.

The captures confirm successful ICMP communication for all three targets with exactly four Echo Requests and four Echo Replies in each capture.
