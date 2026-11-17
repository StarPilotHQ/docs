---
title: Install StarPilot on comma 3, 3X & 4
description: Install StarPilot on comma 3, 3X, or 4 with the official stable and testing installer values, device setup steps, and branch switching instructions.
---

# Installing StarPilot

The StarPilot install links are:

* Stable: `starpilothq/stable`
* Testing: `starpilothq/testing`

If your comma is new or already on the setup screen, skip to the instructions for your device.

If openpilot or another fork is already installed:

1. Park your car and make sure the comma has a good internet connection.
1. Open **Settings > Software**.
1. Select **Uninstall** and confirm.
1. Wait for the comma to restart and return to the setup screen.

## Comma 4

1. Choose **Custom Software** on the setup screen.
1. Connect to Wi-Fi when prompted.
1. Enter `starpilothq/stable` for Stable or `starpilothq/testing` for Testing.
1. Start the installation and let it finish. The comma may restart more than once.

Do not unplug the comma while it is installing or updating AGNOS.

## Comma 3/3X

1. Connect to Wi-Fi on the setup screen.
1. Choose to install custom software.
1. Enter `starpilothq/stable` for Stable or `starpilothq/testing` for Testing.
1. Start the installation and wait for the comma to restart.

You can power the comma inside your home with a suitable USB-C power adapter if the Wi-Fi
signal in your car is poor.

## If You Cannot Open Settings

Use this only if the comma is stuck and you cannot uninstall through **Settings > Software**.

1. Unplug the comma and wait 60 seconds.
1. Plug it back in and immediately tap the screen repeatedly until the reset prompt appears.
1. Reset the device. On Comma 4, swipe to confirm. On Comma 3/3X, tap to confirm.
1. After it returns to setup, follow the instructions above for your device.

> [!NOTE] Recommended settings page
> See [the settings page](../usage/settings.md)

> [!WARNING] Stuck on the boot logo after installing?
> See [the faq](../faq.md#im-stuck-on-the-boot-logo-screen-how-do-i-fix-it)

> [!WARNING] Other install issues
> Message us in [Discord](https://firestar.link/discord)
> or [flash your comma](https://flash.comma.ai) and retry. Make sure you try the steps above
> multiple times before resorting to flashing.

> [!TIP] Want to change settings from your phone?
> Use [the Galaxy](../usage/galaxy.md)

## Branches

StarPilot has two main channels. `dev` remains the maintainer’s personal branch; it is not a recommended user channel:

| Branch | Purpose | Stability |
| --- | --- | --- |
| `stable` | The default branch. Use this unless you have a specific reason not to. | Stable. Recommended for everyone. |
| `testing` | The active testing branch. Changes are made to it regularly and it may break at any time. Commonly used by users who want to test new features or fixes that are still in development. | Unstable. Use at your own risk. |

### Existing installs and the one-time rename

The channel names are changing from `StarPilot` to `stable`, and from `Dom` to `testing`.
The rename release keeps the installed software version and settings. It changes the
local branch and update target once; it does not install the rebase, erase recordings,
remove models, reset calibration, or unpair Galaxy. A later deliberate branch switch
is respected and does not run a chain of renames.

Update normally while parked. After the rename release starts, check that Galaxy’s
installed branch and update target show `stable` or `testing`. Devices can complete
this local rename without a network connection after downloading that release.

If your comma was offline during the rollout, **check the target before updating**.
GitHub does not redirect Git branch names or raw-file installer URLs. If an old branch
has since been reused for different software, do not update it expecting the old
channel. Select `stable` or `testing` explicitly in Galaxy. If the old updater cannot
switch, use the pinned migration release provided in the rollout announcement or
contact support; do not factory-reset or delete your recordings as a first step.

### Changing branches

#### Using [Galaxy](../usage/galaxy.md)

While parked, open **Tools → System Tools → Software & Updates**. Choose a target **Branch**, press **Update**, then confirm **Update & restart**. **Download only** prepares an update without restarting.

#### Direct on device

On the **Comma 3/3X** interface:

1. Go to **Settings**.
1. Open **Software**.
1. Tap **Target Branch** and pick the branch.
1. Click **Select**.
1. Select **Yes** to download.
1. Wait for the download to finish.
1. Install the update.

On the **Comma 4**:

1. Go to **Software**.
1. Turn on **Show advanced options**.
1. Select the branch.
1. Select **Switch + Update**.
