---
title: StarPort — Setup & Troubleshooting
description: Show StarPilot on a car screen or tablet, configure audio and layout, and troubleshoot connections.
---

# StarPort

Open **Galaxy → Tools → StarPort** while parked. Choose your device, follow its setup steps, then connect. Supported setups include built-in Android Auto, AAWireless and Motorola MA1 wireless adapters, and the Open Headunit and HeadunitPad tablet apps. Other adapters and apps may work but are not tested and may be unreliable.

## Set up

1. Under **StarPort Support**, turn on StarPort and choose **Install support**. Download a current stable Android Auto package by Google LLC and upload it without unzipping it. Wait for support to show **Ready**. Wireless pairing needs Bluetooth; accept Galaxy's prompt to enable it if needed.
2. Choose your connection and follow the matching instructions:
    - **Built-in wireless:** Open the car's phone pairing screen, tap **Find car**, select the car, and confirm the pairing code on both screens. Enable wireless Android Auto in the car's settings if needed; it may be called *smartphone connection* or *phone projection*.
    - **Wireless adapter:** Choose the adapter, put it in pairing mode, and tap **Find adapter**. Select the adapter as the receiver. If Galaxy asks you to connect your paired car in Bluetooth first, open **Galaxy → Tools → Bluetooth**, connect the car, and return to StarPort.
    - **USB cable:** Connect the car's Android Auto USB data port to the comma with a data-capable cable, then tap **Connect**. Bluetooth pairing is not needed. In the expanded setup, this option is called **Wired AA**.
    - **Tablet app:** Choose the app, open it on the tablet on the same Wi-Fi network as the comma, then tap **Connect**.
3. Tap **Connect** and keep the car on and its screen awake. The first connection can take a few minutes and sometimes more than one drive while StarPort finds a working setup. Later connections use what worked before.

Enable **Automatic Connection** to connect when you start driving. Use **Setup and Pairing** or **Change how your car connects** to reopen setup.

## Connection problems

Check that StarPort support shows **Ready**, the correct car or adapter is selected, and Bluetooth and wireless Android Auto are enabled when using a wireless receiver. Other paired phones may take the screen first.

| Status | What to check |
| --- | --- |
| **Connecting over Bluetooth** or **Finding Android Auto** | Keep the car on and the selected receiver paired. |
| **Starting wireless setup** or **Waiting for car Wi-Fi** | Enable wireless Android Auto and check whether another phone is using it. |
| **Getting car Wi-Fi details** or **Joining car Wi-Fi** | Follow the displayed instructions; restart the car or adapter if this repeatedly fails. |
| **Securing your connection** | Check the support certificate and update or reinstall support if needed. |
| **Waiting for your USB cable** | Use the car's Android Auto data port and a data-capable cable. |
| **Connected · car screen in use** | Open Android Auto on the car screen to return to StarPilot. |
| **Trying your connection again** | Allow the automatic reconnect and follow any displayed instructions. |
| **Your dashboard is live** | StarPilot is showing on the screen. |

For a black or frozen screen, tap **Disconnect**, wait a few seconds, and connect again. If it keeps happening, turn the car off, wait for its screen to go dark, and restart it. If a wireless adapter hangs repeatedly, unplug it for ten seconds and plug it back in. StarPort continues automatically or offers **Continue**.

Use **Connection Logs** on the StarPort page when asking for help. The logs page includes the last 20 sessions.

## Other phones and audio

Most cars run Android Auto on one device at a time. If another phone keeps taking over, choose the comma as the preferred device where supported, disable that phone's wireless Android Auto for this car, or remove unused pairings.

Open **StarPort → Spotify and Phone Audio** for music and phone audio. For phone audio, pair your phone through [Bluetooth](./bluetooth-controls.md) first.

## Layout, maps, and upkeep

- **Customize Layout** opens the StarPort layout editor.
- **Offline Road Maps** saves road lines for the map overlay. For destinations and other map downloads, see [Navigation & Maps](./navigation.md).
- Wireless projection may use the comma's Wi-Fi for the car instead of its usual network. Use the Galaxy hotspot for local access; remote Galaxy needs an Internet connection on the comma.
- If the support certificate expires soon or has expired, open **StarPort Support** and use **Update** or **Reinstall** as offered.

## Start over

Forget the receiver in Galaxy's **Bluetooth** page and remove the comma from the receiver's paired-device list. Restart the car or adapter, reopen its pairing screen, then follow the matching StarPort setup again.
