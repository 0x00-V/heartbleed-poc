# Heartbleed PoC

This repository contains a simple **Proof of Concept (PoC)** implementation to test for the Heartbleed vulnerability (CVE-2014-0160) on TLS/SSL servers.

---

## Overview

Heartbleed is a critical security bug in the OpenSSL library that allows attackers to read more data than intended from a server’s memory via crafted heartbeat requests. This PoC demonstrates how to trigger the vulnerability by:

- Sending a valid TLS Client Hello to initiate a handshake
- Sending a malicious heartbeat request with an incorrect payload length
- Receiving leaked memory data from the server if vulnerable

---

## Usage

Compile the code with a C++ compiler (Don't forget to change host string and port on line 41 and 42):

```bash
g++ -o heartbleed_poc exploit.c++
```
Run the code:
```bash
./heartbleed_poc
```

You can test this script here: https://tryhackme.com/room/heartbleed
