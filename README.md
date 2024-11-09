# Wifite2Guide


# Wifite2 WPS Cracking Guide

## Overview
This guide provides step-by-step instructions for using Wifite2 on Kali Linux to exploit WPS vulnerabilities in Wi-Fi networks. Wifite2 automates Wi-Fi security auditing, making it easy to assess the security of your network.

> **Disclaimer**: This tool is intended for ethical, educational, and authorized security testing purposes only. Unauthorized usage is illegal and unethical.

---

## Prerequisites

### Operating System
- **Kali Linux**: Ensure you have a functional installation of Kali Linux.

### Required Tools
- **Wifite2**: Pre-installed in Kali Linux. If missing, install it using:
  ```bash
  sudo apt update && sudo apt install wifite
  ```

### Hardware
- **Wireless Adapter**: You need a wireless card capable of packet injection. Recommended models:
  - Alfa AWUS036ACH
  - TP-Link TL-WN722N (v1)

---

## Setup

### 1. Connect Wireless Adapter
- Plug your wireless adapter into your system.
- Verify it is detected by running:
  ```bash
  iwconfig
  ```

### 2. Enable Monitor Mode
- To enable monitor mode, use:
  ```bash
  airmon-ng start wlan0
  ```
  Replace `wlan0` with the actual name of your wireless interface (e.g., `wlan1` or `eth0`).

- Confirm monitor mode is enabled by running:
  ```bash
  iwconfig
  ```
  Look for an interface labeled as **Monitor**.

---

## Using Wifite2 for WPS Cracking

### Step 1: Start Wifite2
Run Wifite2 with the following command:
```bash
sudo wifite
```

### Step 2: Scan for Networks
- Wifite2 will start scanning for available networks.
- Wait for the scanning process to detect nearby networks.

### Step 3: Stop Scanning
- Once you see a list of networks, press `Ctrl+C` to stop the scan.

### Step 4: Select Target Network
- From the displayed list, identify a network with **WPS enabled**. These networks are marked with "WPS" under the encryption details.
- Choose the target by typing its corresponding number.

### Step 5: Crack WPS
- Wifite2 will automatically begin the cracking process.
- It uses techniques such as:
  - **Pixie Dust Attack**: Exploits poor WPS implementation.
  - **Brute Forcing**: Attempts all possible PIN combinations.

### Step 6: Retrieve Results
- If the attack is successful:
  - The WPA key will be displayed.
  - Results will be saved in the following directory:
    ```bash
    /root/wifite/<network_name>.txt
    ```

---

## Troubleshooting

### Wireless Adapter Not Detected
- Ensure your adapter is plugged in properly.
- Install missing drivers, if necessary:
  ```bash
  sudo apt install firmware-misc-nonfree
  ```

### No WPS Networks Found
- Make sure WPS is enabled on the target networks.
- Check for signal interference or move closer to the router.

### Errors During Cracking
- Ensure your wireless adapter is compatible with packet injection.
- Retry with a different method or wait for a better signal.

---

## Key Commands Summary

| Command                          | Description                                   |
|----------------------------------|-----------------------------------------------|
| `iwconfig`                       | Check wireless interfaces and modes          |
| `airmon-ng start wlan0`          | Enable monitor mode on a wireless interface  |
| `sudo wifite`                    | Start Wifite2                                |
| `Ctrl+C`                         | Stop the scanning process                    |
| `/root/wifite/<network_name>.txt`| Path to saved results                        |

---

## Legal Notice
**Use Responsibly**: This tool should only be used for security testing on networks that you own or have explicit permission to test. Unauthorized use is illegal and may result in severe penalties.

By using this guide, you agree to take full responsibility for your actions.
