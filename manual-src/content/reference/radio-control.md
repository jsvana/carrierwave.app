---
title: "Radio Control"
description: "BLE and WiFi radio connection, frequency/mode sync, and supported protocols"
weight: 6
showToc: true
---

Carrier Wave can connect to your radio via Bluetooth Low Energy (BLE) or WiFi to synchronize frequency and mode between the Logger and your transceiver. This eliminates manual frequency entry and ensures your log always matches your radio's actual operating parameters.

## Overview

Radio Control provides:

- **Automatic frequency sync** - Logger frequency updates when you tune the radio
- **Mode sync** - Logger mode changes when you switch modes on the radio
- **Bidirectional control** - Change frequency in the Logger and the radio follows
- **Background operation** - Connection persists across app screens and during recording

## Connection Transports

Carrier Wave supports two connection transports:

### Bluetooth Low Energy (BLE)

Connect to radios with built-in Bluetooth or via third-party BLE-to-serial adapters. BLE is the default transport and works with all supported protocols.

### WiFi

Connect to Icom radios with built-in WiFi (e.g., IC-705) via Access Point or Station mode. The radio acts as a WiFi access point that your iOS device joins, or both devices connect to the same local network.

**WiFi setup:**

1. On your radio, enable WiFi and note the Access Point SSID and password (or configure Station mode for your local network)
2. On your iOS device, join the radio's WiFi network
3. In Carrier Wave, go to **Settings -> Radio** and select **WiFi** as the transport
4. Enter the radio's IP address (default: `192.168.1.1` for AP mode)
5. Carrier Wave connects via TCP and begins frequency/mode sync

**WiFi advantages over BLE:**
- More reliable connection (no BLE dropouts during TX)
- Higher data throughput for scope/waterfall data (CW Sweep)
- No pairing required — just network connectivity

## Supported Protocols

Carrier Wave supports three radio control protocols via BLE or WiFi:

### Icom CI-V

The CI-V (Communication Interface V) protocol supports Icom radios via BLE or WiFi:

- **Supported radios:** IC-705, IC-7300, IC-7610, IC-7851, IC-9700, and other CI-V compatible models
- **Commands:** Frequency read/write, mode read/write, S-meter read
- **CI-V address:** Configurable per radio (default varies by model; IC-705 is `0x94`)
- **Baud rate:** Auto-detected from the BLE interface

### Kenwood / Elecraft Text Protocol

Text-based command protocol for Kenwood and Elecraft radios:

- **Supported radios:** Kenwood TS-890S, TS-590SG; Elecraft KX2, KX3, K4
- **Commands:** `FA` (frequency A), `MD` (mode), `SM` (S-meter)
- **Format:** ASCII text commands terminated with `;`

### Yaesu CAT

Computer Aided Transceiver (CAT) protocol for Yaesu radios:

- **Supported radios:** FT-891, FT-991A, FTDX10, FTDX101D
- **Commands:** Frequency, mode, power, metering
- **Format:** Binary command packets

## Device Scanning

### Starting a Scan (BLE)

1. Go to **Settings -> Radio**
2. Select **BLE** as the transport
3. Tap **Scan for Radios**
4. Carrier Wave scans for BLE devices advertising serial port services

### Scan Results

Each discovered device shows:

- **Device name** (e.g., "IC-705 BT", "KX3-12345")
- **Signal strength** (RSSI in dBm)
- **Connection status** (Available, Previously Paired, Connected)
- **Protocol hint** (if the device name matches a known radio)

### BLE Interfaces

If your radio doesn't have built-in BLE, you can use a third-party BLE-to-serial adapter. Carrier Wave works with standard BLE serial port profile (SPP) devices.

## Connection Setup

### First-Time Pairing

1. Ensure your radio's Bluetooth is enabled and discoverable
2. Tap the device in the scan results
3. Select the correct **protocol** (Icom CI-V, Kenwood/Elecraft, or Yaesu CAT)
4. For Icom radios, enter the **CI-V address** (hex, e.g., `94`)
5. Tap **Connect**

Carrier Wave attempts to read the current frequency as a connection test. If successful, the device is saved for automatic reconnection.

### Automatic Reconnection

After initial setup, Carrier Wave automatically reconnects to your saved radio when:

- The app launches and the radio is in range
- The radio is powered on while the app is running
- Bluetooth connectivity is restored after a dropout

### Connection Status

The radio connection status appears in the Logger header:

- **Green radio icon** - Connected and syncing
- **Yellow radio icon** - Connecting or reconnecting
- **Gray radio icon** - Disconnected
- **No icon** - Radio control not configured

## Frequency & Mode Sync

### Radio-to-Logger (Read)

When connected, Carrier Wave polls the radio for frequency and mode changes:

- **Polling interval:** 200ms for responsive sync
- **Frequency resolution:** 1 Hz (displayed in MHz with appropriate precision)
- **Mode mapping:** Radio modes are mapped to Carrier Wave's mode list (e.g., CI-V mode `03` -> CW)

When you tune the radio's VFO, the Logger frequency updates within approximately 200ms.

### Logger-to-Radio (Write)

When you change frequency in the Logger (via command, band picker, or spot tap):

- The radio re-tunes to the new frequency
- The radio switches to the appropriate mode
- A confirmation read-back verifies the radio accepted the change

### Mode Mapping

| CI-V Mode | Kenwood Mode | Yaesu Mode | Carrier Wave Mode |
|-----------|-------------|------------|-------------------|
| 00 (LSB) | MD1 | 01 | SSB |
| 01 (USB) | MD2 | 02 | SSB |
| 03 (CW) | MD3 | 03 | CW |
| 04 (RTTY) | MD6 | 06 | RTTY |
| 05 (AM) | MD5 | 05 | AM |
| 08 (FM) | MD4 | 04 | FM |
| 17 (DATA) | MD9 | 0C | FT8/DATA |

Sideband selection (LSB vs USB) follows band conventions and is handled automatically.

## Radio Settings

Configure radio control behavior in **Settings -> Radio**:

### Transport Selection

Choose **BLE** or **WiFi** as the connection transport. WiFi is currently supported for Icom CI-V radios only.

### Protocol Selection

Choose Icom CI-V, Kenwood/Elecraft, or Yaesu CAT. This determines the command format used for communication.

### CI-V Address

For Icom radios only. Enter the hex CI-V address of your radio. Common defaults:

| Radio | Default CI-V Address |
|-------|---------------------|
| IC-705 | 0xA4 |
| IC-7300 | 0x94 |
| IC-7610 | 0x98 |
| IC-9700 | 0xA2 |

### Sync Direction

- **Bidirectional** (default) - Radio and Logger sync both ways
- **Radio -> Logger only** - Logger follows radio, but Logger changes don't control the radio
- **Logger -> Radio only** - Radio follows Logger commands only

### Auto-Connect

Toggle automatic reconnection when the saved radio is detected.

## Troubleshooting

### Radio Not Found

- Ensure Bluetooth is enabled on both the radio and iOS device
- Check that the radio is in discoverable/pairing mode
- Move the devices closer together (BLE range is typically 10-30 meters)
- Restart Bluetooth on both devices

### Connection Drops

- BLE connections can be affected by RF interference from the radio itself
- Position the iOS device away from the antenna feedline
- Some radios disconnect BLE during transmit; Carrier Wave reconnects automatically

### Frequency Not Syncing

- Verify the correct protocol is selected
- For Icom radios, confirm the CI-V address matches the radio's setting
- Check that the radio's CI-V transceive mode is enabled (if available)

## See Also

- [Logger](/reference/logger/) - Session management and frequency entry
- [FT8 Operating Suite](/reference/ft8/) - FT8 with radio control
- [Settings & Services](/reference/settings/) - Radio control configuration
