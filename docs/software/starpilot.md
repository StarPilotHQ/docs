---
title: Install StarPilot on comma 3, 3X & 4
description: Install StarPilot on comma 3, 3X, or 4 with the current installer values and channel names, device setup steps, and branch switching instructions.
---

# Installing StarPilot

The StarPilot install links are:

* Stable: `starpilothq/stable`
* Testing: `starpilothq/testing`

If StarPilot is already installed, see [Changing branches](#changing-branches).

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

A factory reset erases stored content and settings on the comma. Download any recordings
or logs you need first, if the device is still accessible.

1. Unplug the comma and wait 60 seconds.
1. Plug it back in and immediately tap the screen repeatedly until the reset prompt appears.
1. On comma 4, tap **reset & erase**, then swipe to confirm. On comma 3/3X, follow the **Confirm** prompts.
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

StarPilot currently has two main channels:

| Branch | Purpose | Stability |
| --- | --- | --- |
| `stable` | Stable releases. Use this unless you have a specific reason not to. | Stable. Recommended for everyone. |
| `testing` | The active testing branch. Changes are made to it regularly and it may break at any time. Commonly used by users who want to test new features or fixes that are still in development. | Unstable. Use at your own risk. |

### Channel names and the one-time migration

The testing channel is now `testing`, formerly `Dom`. `Dom` remains a compatibility
bridge for existing devices and old install links; future updates and development
continue on `testing`.

The stable channel is `stable`, formerly `StarPilot`. The old `StarPilot` install
link and update channel also move once to `stable`. This naming change keeps
version 6.7.9; it does not upgrade to the rebase. `dev` is reserved for the
maintainer’s personal work, not a recommended user channel.

The migration release keeps the installed software version and settings. It changes the
local branch and update target once; it does not install the rebase, erase recordings,
remove models, reset calibration, or unpair Galaxy. A later deliberate branch switch
is respected and does not run a chain of renames.

Update normally while parked. After the migration release starts, Galaxy’s installed
branch and update target show `stable` for old StarPilot installs, or `testing` for
old Dom installs. Devices can complete this local rename without a network
connection after downloading the release.

The old `StarPilot` and `Dom` links remain available for devices that update later.
GitHub does not redirect branch names; these preserved compatibility releases
perform the one-time switch locally.

### Changing branches

#### Using [Galaxy](../usage/galaxy.md) (Recommended)

<span id="using-galaxy"></span>

Park and turn off the vehicle; keep the comma powered and online.
In Galaxy, open **Tools → System Tools → Software & Updates**.
Under **Advanced options → Branch**, choose **Stable** or **Testing**.

To update to the latest version of a branch:

1. Select **Update**. Confirm **Update & restart**, or **Restart & install** if the update
   is already prepared.
1. If an update was installed, wait for the device to restart and Galaxy to reconnect.
   An up-to-date branch needs no restart.

If Galaxy cannot verify the update after five minutes, check the connection and the
installed version before trying again.

To choose a specific version instead:

1. Select a version from the list.
1. Choose **Install selected version** or **Download and install selected version**.
1. Confirm the restart and wait for Galaxy to reconnect.

Choosing a branch or version does not install it. **Download only** prepares a version for
later installation.

#### Direct on device

With the vehicle off and comma powered and online, open **Settings → Software**.
If **Target Branch** is shown, select `stable` or `testing`. Otherwise, choose the branch
in Galaxy.

On the **Comma 3/3X** interface:

1. Use **CHECK**, then **DOWNLOAD** when offered.
1. Wait for the download to finish.
1. Select **Install Update → INSTALL** and wait for the device to restart.

On the **Comma 4** interface:

1. Use **check for update**, then **download update** when offered.
1. Wait for the download to finish.
1. Select **install now** and wait for the device to restart.

### Automatic updates

**Download updates automatically** prepares updates while the vehicle is off.
**Install updates automatically** restarts the device on the configured schedule, only while
the vehicle is off. These are separate settings. Configure the **Automatic restart schedule**
and its time zone under **Advanced options** in Galaxy.

### Returning to the previous version

In Galaxy, choose **Select previous version**, then **Install selected version**, and confirm
**Restore previous version**. Restoring turns off automatic downloads.

Fast Update and previous-version restore depend on compatible saved software and the installed
operating system. If the updater requires a full update, use the normal download/install path
instead.
