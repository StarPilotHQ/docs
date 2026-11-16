---
title: Chestnut External GPU Support
description: Learn about StarPilot support for the Chestnut external GPU on comma 3, 3X, and 4, including when larger driving models need an eGPU.
---

# Chestnut (External GPU)

**Chestnut** is comma.ai's external GPU (eGPU) dock. It connects a desktop graphics card to your comma device over USB4, giving openpilot far more compute than the built-in chip can provide on its own.

StarPilot fully supports Chestnut on the **Comma 3**, **Comma 3X**, and **Comma 4**.

Learn more from comma.ai: [Introducing chestnut](https://blog.comma.ai/chestnut/) · [Chestnut shop](https://comma.ai/shop/chestnut)

## What does Chestnut do?

Comma devices are built around low-power, on-device inference — roughly a 10 W compute budget. That works well for most driving models, but newer **chestnut-class models** are much larger and need a desktop GPU to run in real time.

Chestnut bridges that gap. You mount a GPU in the passenger footwell or under the passenger seat, connect it to 12 V power, and plug a USB cable into your comma device. At startup, model weights load over USB4; after that, inference runs entirely on the GPU.

## Do I need Chestnut?

Most StarPilot driving models run on the comma device's built-in compute. Chestnut lets you run supported Big models locally and is required for **Model pair**. **Jetlink** is another option for running a single Big model on a remote host; see [Models](../usage/model-manager.md).

On [Galaxy’s Models page](../usage/model-manager.md):

- Models that need external hardware are labeled accordingly on the Models page.
- You can download a Big model before connecting Chestnut. It runs only when compatible GPU hardware is ready.
- Without an external GPU or an active Jetlink host, StarPilot uses **Active Small**. Your Big selection remains saved.

StarPilot checks for Chestnut at boot.

## Hardware options

Comma sells **tiny chestnut**, a dock that needs your own GPU and power supply, and **Ready to drive**, a kit with GPU and power hardware. See [comma's shop](https://comma.ai/shop/chestnut) for current options.

## Setup overview

This is a high-level summary. Follow comma's included instructions (or their blog) for the full install:

1. Assemble Chestnut with your GPU and connect GPU power.
2. Mount Chestnut in the passenger footwell or under the passenger seat.
3. Connect Chestnut to 12 V vehicle power (cigarette lighter or similar).
4. Run the USB cable from Chestnut to your comma device's USB4 port.
5. Boot StarPilot — the device should detect Chestnut automatically.

> [!NOTE] Firmware
> Chestnut ships with custom firmware that StarPilot recognizes. The device checks that the firmware is ready before enabling GPU models. If GPU models stay unavailable after connecting Chestnut, ask in [Discord](https://firestar.link/discord).

> [!TIP] Driving models
> See [Models](../usage/model-manager.md) for the current catalog. Most users should start with an on-device model.
