---
title: Models
description: Choose a single driving model, pair steering and speed models, and manage downloads and Jetlink in Galaxy.
---

# Models

Open **Galaxy → Tools → Models** to choose what drives your car and manage downloads.

The driving model processes camera video and plans steering and acceleration or braking. Preferences vary with your car, roads, region, and conditions. Use the current catalog and community favorites, and ask for feedback in [Discord](https://firestar.link/discord).

## Single model

- **Active Small · On-device:** The model that runs on the comma's built-in compute.
- **Active Big · External:** A larger model for compatible external hardware. Choose **None - always use Active Small** to keep using the on-device model.

[Chestnut](../hardware/chestnut.md) is supported on comma 3, 3X, and 4. You can download a Big model before connecting it. Without an external GPU or an active Jetlink host, Active Small is used and your Big selection stays saved. Jetlink can also run a Big model on a remote host, as described below.

Selections take effect the next time the driving model starts. **Running now** reports the loaded model; a saved selection does not mean it is already running.

**Model Randomizer** chooses a different installed, verified model each start. Use **Include in Randomizer** to exclude individual models. Favorites do not change the random pool.

## Model pair

Model pair combines one model's **Lateral model** (steering and path) with another's **Longitudinal model** (speed and lead pacing).

1. Turn off the vehicle before changing the pair. Connect a firmware-ready Chestnut; the pair runtime must also be available.
2. Use **Show pairable models** to find supported models and download their pair variants. Ordinary on-device downloads alone do not establish that a pair variant is ready.
3. Choose **Model pair**, then select two different downloaded models for **Lateral model** and **Longitudinal model**. Valid selections save automatically and take effect the next time the driving model starts.
4. Check **Running now** and the pair status to confirm what is actually running.

At least one model must have a Chestnut variant. Two Big models cannot run together at the required speed; choose a Small model for at least one role. Pairing increases inference time, and other combinations can also cause model lag warnings. When available, the comma GPU runs one Small role while Chestnut runs the other.

Your Small and Big selections remain saved as fallback choices. Choose **Single model** to disable pairing and return to those selections at the next start.

## Downloads

Browse **On the comma**, **Needs GPU or Jetlink**, or **All**. Search by model name, filter favorites or pairable models, and sort by release date, name, or size. Download individual models or use **Download all**. Progress and retry controls appear on this page. Park before downloading.

## Jetlink

Under **Jetlink → Remote model connection**, choose **USB computer** or **iPhone / iPad**. Set up while parked with a USB 3 data cable and separate power. Keep the computer awake, or the iPhone app open and unlocked. Jetlink stays off while Chestnut is connected.

Jetlink runs Active Big on its host, which downloads the model itself. **Prepared** means the remote model is built, rather than active. The local Small model remains available, and your local Small and Chestnut selections stay saved.

Follow the [Jetlink setup guide](https://github.com/StarPilotHQ/StarPilot/blob/testing/openpilot/starpilot/models/JETLINK.md) for host setup.
