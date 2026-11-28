---
title: Chevrolet Bolt EV Hardware & Setup
description: Choose hardware for StarPilot on Chevrolet Bolt EV, including ACC and non-ACC setups, comma pedal requirements, limitations, and pedal firmware.
---

# Bolt Hardware

## Vehicle Quirks

Things to be aware of for your vehicle:

* Steering assistance has a minimum operating speed of approximately 7 mph. Be ready to steer at low speeds.
* On supported non-ACC Bolts, the [Comma Pedal](../hardware/comma-pedal.md) uses regen in one-pedal or L mode to slow the vehicle. StarPilot has no access to friction brakes, so deceleration can be limited, especially at low speed. Be ready to brake manually.
* On supported ACC Bolts, StarPilot can request friction braking through the factory ACC system. Regen is limited to 10kW. Installing a [Comma Pedal](../hardware/comma-pedal.md) adds stronger regen (up to 70kW) and supports starting from a stop (stop and go). See [ACC Bolts](#acc-bolts).
* The regen paddle will disengage StarPilot throttle/brake control.

## Car Configuration

### StarPilot Settings

In Galaxy, open **Toggles → Vehicle**. With the car off, manually select the exact registered vehicle fingerprint that matches your configuration. Do not use any fingerprint containing ACC if you do not have ACC.

### Tires

* Use the pressures recommended for your vehicle and tires.
* Keep your car wheels aligned.
* Check the vehicle manufacturer’s guidance before changing wheel or tire sizes. Keep in mind that non-stock tire sizes will affect the lateral performance of StarPilot.

### One Pedal Driving/L Mode

On Bolt setups that use the Comma Pedal for regen braking, use One Pedal mode on 2022-2023 models or L mode on 2017-2021 models.

### Sport Mode

On 2022–23 Bolts, enabling Sport Mode will reduce available steering torque.

## Vehicle Requirements

### Lane Keep Assist System (LKAS)

As with most openpilot compatible cars, the Bolt must be equipped with LKAS (Lane Keep
Assist System) in order for openpilot to send steering commands.

#### Trim Levels with LKAS
> [!WARNING] Unofficial list
> Just a guide to help new users. Please do your own research.

* 2017-18 EV: Premier trim with Driver Confidence II package [^1] [^2]
* 2019-21 EV: Any trim with Driver Confidence II package [^3] [^4] [^5]
* 2022-23 EV: All trim levels [^6] [^8]
* 2022-23 EUV: All trim levels *without super cruise** [^7] [^9]

### Does your Bolt have Adaptive Cruise Control (ACC)?

Both ACC and non-ACC are compatible with StarPilot,
but vary slightly in hardware recommendations.

#### Trim Levels with ACC

* 2022–23 EV: 2LT trim with the Adaptive Cruise Control Package [^6] [^8]
* 2022–23 EUV: Premier or Premier Redline without the Super Cruise package [^7] [^9]

## Openpilot Hardware List for Bolt

1. [Comma 4](../hardware/comma.md)
2. [GM Harness and Harness Box](../hardware/gm-harness.md)
3. [Comma Pedal](../hardware/comma-pedal.md) (optional, but ***strongly recommended for non-ACC cars***)

{% include-markdown "../hardware/embed/beartech.md" %}
{% include-markdown "../hardware/embed/comma-power.md" %}

### Should I buy a Comma Pedal?

Our recommendation for whether or not to purchase the pedal depends on if your car is
[ACC](#acc-bolts) or [Non-ACC](#non-acc-bolts).

#### Non-ACC Bolts

On supported non-ACC Bolts, the Comma Pedal is ***strongly recommended***.
It lets StarPilot accelerate and use regen braking in One Pedal or L mode.
Braking and restarting from a stop depend on the vehicle and pedal setup.

Without the pedal, supported configurations use
[CC Long, also called Redneck ACC](./volt.md#what-is-redneck-acc-aka-cc-long)
to adjust factory cruise. The Bolt CC Long profiles require at least 24 mph to engage.
Be ready to brake manually.

#### ACC Bolts

On supported ACC Bolts, StarPilot can use ACC commands for gas and friction braking. Without a pedal, you may need to use the accelerator or cruise resume to move again from a stop.

A compatible [Comma Pedal](../hardware/comma-pedal.md) is optional. Supported ACC-plus-pedal configurations can blend pedal-based regen with ACC friction braking and can support stop-and-go. Confirm the setup for your vehicle before ordering hardware.

## Pedal Firmware Flashing

> [!WARNING] Gen 1 Bolts only (2017-2021)
> If you see a propulsion error with a pedal installed, check the
> [supplier's guidance](https://docs.innoisle.com/beartech/comma-pedal-description-and-installation-guide)
> and confirm the firmware for your exact pedal before flashing.
> Ask in [Discord](https://firestar.link/discord) if you need help identifying the right build.

The downloads below match [BearTech's May 1, 2025 StarPilot build](https://github.com/fraserxiong/panda_firmware/commit/fbe3e17de8d61f3e11d60948cb3e2ba40390263f).

### Required Resources

* [DFU Key](https://shop.beartech.ca/products/dfu-key)
* [bootstub.pedal.bin](../assets/pedal-firmware/gen1-bolt/bootstub.pedal.bin){:download="bootstub.pedal.bin"}
* [pedal.bin](../assets/pedal-firmware/gen1-bolt/pedal.bin){:download="pedal.bin"}

> [!NOTE] USB cable requirement
> Use a USB data cable and follow the
> [supplier's DFU key instructions](https://docs.innoisle.com/beartech/dfu-key-flash-instructions-and-firmware)
> for your key and pedal. If the computer cannot detect the key, check those connections
> before attempting a flash.

### Flashing Instructions

[Flash Comma Pedal in DFU Mode Tutorial from TinyBear](https://www.youtube.com/watch?v=DNf0OGwXUUQ)

### Other Firmware

See [TinyBear's firmware branches](https://github.com/fraserxiong/panda_firmware/branches)
for other pedal builds. Confirm which branch matches your setup.

## Troubleshooting

### Propulsion Power Reduced and Regen Not Working

Your Bolt may have had a momentary issue communicating with the throttle pedal.

With the vehicle off, inspect and reseat the pedal connections using the [hardware supplier’s instructions](https://docs.innoisle.com/beartech/comma-pedal-description-and-installation-guide). If propulsion or pedal faults remain, stop using the setup and [ask for help](../ticketsystem.md).

[^1]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2017-bolt.pdf
[^2]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2018-bolt.pdf
[^3]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2019-bolt.pdf
[^4]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2020-boltev.pdf
[^5]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2021-boltev.pdf
[^6]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2022-boltev.pdf
[^7]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2022-bolteuv.pdf
[^8]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2023-boltev.pdf
[^9]: https://cdn.dealereprocess.org/cdn/brochures/chevrolet/2023-bolteuv.pdf
