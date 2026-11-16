---
title: Galaxy & StarPilot Features
description: Find StarPilot features in Galaxy and learn what its pages and key controls do.
---

# Galaxy & Features

Galaxy is StarPilot's browser interface for settings, models, routes, and device tools. Feature availability depends on your [car](../cars/support.md) and [hardware](../hardware/comma.md). Read [operation](./operation.md) for driving behavior.

## Access Galaxy

- **StarPilot Companion (preferred):** The official iOS and Android app is in closed testing. [Ask in Discord](https://firestar.link/discord) for access. It opens Galaxy over StarPilot Wi-Fi, a shared network, or Bluetooth for basic controls. Optional phone GPS can help navigation. Android app by [@dirwin31](https://github.com/dirwin31): [StarPilotAndroid repository](https://github.com/dirwin31/StarPilotAndroid). iOS app by Nate ([@natehuby76](https://github.com/natehuby76)): [iOS repository](https://github.com/natehuby76/ios-clone).
- **Local browser:** Put your phone or computer and comma on the same Wi-Fi or Ethernet network. On the comma, open **Settings → Device → Galaxy** or **Pair with Galaxy**. Scan the **local** QR code or open `http://<comma-ip>:8082/`. The **Galaxy Access & Install → Local access** panel also lists the address. Direct local access needs no Galaxy password.
- **Remote browser:** While parked, choose **Set password & pair** or **Pair with Galaxy** on the comma. You can also press **Pair** in local **Galaxy Access & Install**. Set a password of at least eight characters. The separate **remote** QR code opens a unique `galaxy.firestar.link` URL. Save it, then sign in with your password. Remote access needs Internet and the Galaxy tunnel, which may take a few minutes to connect. Bookmark each comma's link if you use more than one.
- **Installed web app:** Open your remote link and choose **Install web app** or your browser's **Add to Home Screen**. This web app uses the remote link and needs Internet. For offline browser access, enable **Galaxy Wi-Fi Hotspot** while parked, set its password, then use `http://172.31.254.1:8082/`.

To stop remote access, open **Settings → Device → Galaxy → Unpair remote Galaxy** on the comma, or press **Unpair** in local **Galaxy Access & Install**. The old remote link stops working. Local access on port 8082 remains available. Pair again to get a new remote link.

Keep the remote password and the **App key** shown in Galaxy private. The App key grants remote access.

## Main

- **Home:** Device status, drive totals, and recent drives. Open a drive to see its route.
- **Toggles:** Search or browse settings. Confirm **Save** after a change. Some settings require Park.
- **Tools:** Open a tool below. Unavailable tiles require a connection to your comma.

## Routes

**Routes** lists saved drives. Open one and choose **Footage** for camera video or **Replay with UI** for the driving screen. Replay needs saved logs. **Export segment** saves one clip. **Export route** combines replayable clips.

## Tools

| Tool | Use it to |
| --- | --- |
| **[Bluetooth](../exclusive/bluetooth-controls.md)** | Pair phones and accessories, manage audio connections, and map controller buttons. |
| **[Cameras & Monitoring](../exclusive/cameras-and-monitoring.md)** | Set blind spot previews and Sentry capture, inspect visual monitoring, and take snapshots. |
| **Colors & Layout** | Customize or reset driving widgets, colors, and road views for Big and Small layouts. |
| **Logs & Diagnostics** | Inspect crashes, device and vehicle status, changed settings, and support logs. |
| **[Models](./model-manager.md)** | Choose a single model or pair steering and speed models; manage downloads and Jetlink. |
| **[Navigation & Maps](../exclusive/navigation.md)** | Plan routes, save places, and download road overlays or regional speed-limit and curve data. |
| **Plots & Analysis** | Graph live control signals and controller terms, and review FLM Auto Learn results. |
| **[StarPort](../exclusive/starport.md)** | Show StarPilot on a car screen and configure its layout, maps, and audio. |
| **System Tools** | Switch software branches, manage updates, and review version history. |
| **Vehicle Controls** | Select automatic or manual vehicle identification for the next start. |
| **Galaxy Access & Install** | Manage remote access, app installation, and the local Wi-Fi hotspot. See [Access Galaxy](#access-galaxy). |

## Features at a glance

| Feature | What you can do | Requirements and limits |
| --- | --- | --- |
| [Galaxy](./galaxy.md) | Manage settings, models, software, logs, and recordings from a browser. | Pair your device; remote access requires connectivity. |
| [Driving models](./model-manager.md) | Choose a single model or a steering/speed pair. | Model availability depends on hardware; some need Chestnut. |
| [Navigation](../exclusive/navigation.md) | Set destinations in Galaxy and give the model route guidance. | Requires a Mapbox key and navigation toggles. The driver remains responsible for turns and exits. |
| [Lane Centering](../exclusive/lane-centering.md) | Bias the model's path toward the center of detected lane lines. | Experimental; falls back to the normal model path when conditions are unsuitable. |
| [Speed Limit Controller](../exclusive/speed-limit-controller.md) | Configure speed-limit sources, offsets, confirmation, and fallback behavior. | Source availability varies, and reported limits can be wrong. |
| [Sentry Mode](../exclusive/sentry-mode.md) | Review images captured after sustained movement while parked. | Experimental; uses the device accelerometer and requires the device to remain powered. |
| [Bluetooth controls](../exclusive/bluetooth-controls.md) | Pair audio devices and map controller buttons to favorites. | Experimental; check the guide for tested accessories and pairing steps. |

## Galaxy tuning and support

Galaxy’s tuning tools include live plots, lateral tuning, and a view of settings that differ from
defaults. These help you describe a problem when [opening a support ticket](../ticketsystem.md).

For connection and pairing instructions, see [Access Galaxy](#access-galaxy).

## Driving models and optional Chestnut support

Use [Models](./model-manager.md) for **Single model**, **Model pair** (formerly Model Laboratory), downloads, and Jetlink. Most models run on the comma itself; Big models need compatible external hardware. The guide explains Chestnut requirements, fallback choices, pairing limits, and when saved selections take effect.

## Navigation through Galaxy

Search for a destination, compare routes, and save favorites in Galaxy. StarPilot sends route
information to the comma device, displays turn instructions, and provides upcoming maneuver
information for route guidance.

Enable **Navigation** and save a public Mapbox token in **Navigation & Maps → Setup**; see the [navigation settings](./settings.md#navigation).
Navigation is a driving aid: it does not guarantee the car will complete a route or make an exit.

[Configure navigation](./settings.md#navigation) and [learn how route guidance works](../exclusive/navigation.md).

## Steering, speed, and driving preferences

StarPilot offers settings for lateral tuning, driving personalities, curve speed control,
and switching between Chill and Experimental modes. Availability and behavior depend on
your vehicle's steering and longitudinal capabilities.

The experimental **Lane Centering** feature adjusts the model's path using detected lane
lines when conditions allow. Its settings include lane offset and the model's authority
to deviate from the lane center. This particular feature is separate from the general
lane-centering assistance provided by openpilot.

**Speed Limit Controller** can use map data, supported dashboard limits, and optional
camera-based sign detection. You can require confirmation before applying a new limit,
set offsets, and choose what happens when source data is missing.

Start with the [settings guide](./settings.md), then read the
[operation guide](./operation.md) for the behavior and limitations of driving controls.

## Sentry Mode and Bluetooth accessories

**Sentry Mode** detects sustained movement through the comma device's accelerometer while
parked and captures camera images. Galaxy provides event history, sensitivity settings,
and notification options. It is motion-triggered event capture; it does not continuously
watch camera video for every person passing the car.

**Bluetooth** support is available on comma 3, 3X, and 4 for audio and controller input.
Galaxy provides pairing and button mapping. The comma 3 and 3X also have Bluetooth
management in the on-device Big UI. Both Sentry Mode and Bluetooth are documented as experimental.

[Set up Sentry Mode](../exclusive/sentry-mode.md) or [pair Bluetooth accessories](../exclusive/bluetooth-controls.md).

## Supported devices and cars

StarPilot supports comma 3, 3X, and 4, but device support does not establish compatibility
with a particular car. The vehicle's year, trim, steering system, ACC configuration, and
installed harness or pedal determine which controls are available.

StarPilot's vehicle work extends beyond GM. The compatibility guide lists additions and
improvements across multiple manufacturers, while the car guides explain specific hardware setups.

- [Compare comma devices](../hardware/comma.md).
- [Check vehicle compatibility](../cars/support.md).
- [Find car setup guides](../cars/all.md).
- [Install StarPilot](../software/starpilot.md).

## Shared work and project development

StarPilot builds on openpilot and work from the wider community. Features such as Always On Lateral,
Conditional Experimental Mode, themes, and Speed Limit Controller have shared project
history; their presence alone does not make them exclusive to StarPilot. The
[StarPilot project README](https://github.com/StarPilotHQ/StarPilot#features) describes
the project's features.

For questions about a feature on your car or software branch, use the
[StarPilot support channels](../ticketsystem.md). StarPilot remains driver assistance and
requires an attentive driver ready to take control.
