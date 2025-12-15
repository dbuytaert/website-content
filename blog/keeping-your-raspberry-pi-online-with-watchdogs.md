---
title: 'Keeping your Raspberry Pi online with watchdogs'
date: '2025-03-05T16:48:25-05:00'
author: Dries
summary: 'How hardware and software watchdogs keep your Raspberry Pi running by detecting failures and triggering automatic reboots in hard to get to locations.'
image: blog/raspberry-pi-4-enclosure
tags:
  - 'Solar power'
  - 'Raspberry Pi'
  - Automation
featured: false
published: true
type: blog
url: /keeping-your-raspberry-pi-online-with-watchdogs
id: 5771
---

A while back, I built a [solar-powered, self-hosted website](https://dri.es/my-solar-powered-and-self-hosted-website). Running a website entirely on renewable energy felt like a win, until my Raspberry Pi Zero 2 W started *ghosting* me.

[image miscellaneous-2024/solar-panel-on-roofdeck lazy=false priority=true]

Every few weeks, it just disappears from the network: no ping, no SSH. Completely unreachable, yet the power LED stays on. The SD card has plenty of free space.

The solar panel and battery aren't the problem either. In fact, [my solar dashboard](https://dri.es/sensors/solar) shows they've been running for 215 days straight. Not a glitch.

Every time my Raspberry Pi goes offline, I have to go through the same frustrating ritual: get on the roof, open the waterproof enclosure, disconnect the Pi, pull the SD card, go to my office, reformat it, reinstall the OS and reconfigure everything. Then climb back up and put everything back together.

[image blog/raspberry-pi-4-enclosure]

A month ago, I was back on the roof deck, battling Boston winter. My fingers were numb, struggling with tiny screws and connectors. This had to stop.

The Raspberry Pi Zero 2 W is a great device for IoT projects, but only if it can run unattended for years.

### Watchdogs: a safety net for when things go wrong

Enter **watchdogs**: tools that detect failures and trigger automatic reboots. There are two types:

1. **Hardware watchdog** – Recovers from **system-wide freezes** like kernel panics or hardware lockups, by forcing a low-level reset.
2. **Software watchdog** – Detects and fixes **service-level failures**, such as lost network connectivity, high CPU load or excessive RAM usage.

Running both ensures the Raspberry Pi can recover from minor issues (like a dropped connection) and system crashes (where everything becomes unresponsive).

### Hardware watchdog

The hardware watchdog is a timer built into the Raspberry Pi's Broadcom chip. The operating system must reset or *pet* the timer regularly. If it fails to do so within a set interval, the watchdog assumes the system has frozen and forces a reboot.

Since support for the hardware watchdog is built into the Raspberry Pi's Linux kernel, it simply needs to be enabled.

Edit `/etc/systemd/system.conf` and add:

```shell
 RuntimeWatchdogSec=10s
ShutdownWatchdogSec=10min
```

- `RuntimeWatchdogSec` – Defines how often the watchdog must be reset. On the Raspberry Pi, this must be less than 15–20 seconds due to hardware constraints.
- `ShutdownWatchdogSec` – Keeps the watchdog active during shutdown to detect hangs.

Restart `systemd` to activate the watchdog:

```shell
 $ sudo systemctl daemon-reexec
```

Once restarted, `systemd` starts petting the hardware watchdog timer. If it ever fails, the Raspberry Pi will reboot.

To ensure full recovery, set all critical services to restart automatically. For example, my web server starts by itself, bringing [my solar-powered website](https://solar.dri.es/) back online without any manual work.

### Software watchdog

The hardware watchdog catches complete system freezes, while the software watchdog monitors network connectivity, CPU load and other metrics.

To install the software watchdog:

```shell
$ sudo apt update
$ sudo apt install watchdog
```

Next, edit `/etc/watchdog.conf` and add the following settings:

```shell
# Network monitoring
ping = 8.8.8.8
ping = 1.1.1.1
ping-count = 5

# Interface monitoring
interface = wlan0

# Basic settings
watchdog-device = none
retry-timeout = 180
realtime = yes
interval = 20
```

What this does:

- `ping = 8.8.8.8 / ping = 1.1.1.1` – Checks that the Pi can reach Google (8.8.8.8) and Cloudflare (1.1.1.1).
- `interface = wlan0` – Ensures the Wi-Fi interface is active.
- `retry-timeout = 180` – Reboots the Pi if these checks fail for 180 seconds.
- `interval = 20` – Performs checks every 20 seconds.
- `watchdog-device = none` – Instead of using the hardware watchdog, the daemon monitors failures and triggers a software reboot through the operating system.

While I'm just monitoring the network, you can also configure the watchdog to check CPU usage, RAM or other system health metrics.

Once configured, enable and start the watchdog service:

```shell
$ sudo systemctl enable watchdog
$ sudo systemctl start watchdog
```

*Enabling* the watchdog makes sure it launches automatically on every boot, while *starting* it activates it immediately without requiring a restart.

### Debugging watchdog reboots

When a watchdog triggers a reboot, system logs can help uncover what went wrong. To view all recent system boots, run:

```shell
$ journalctl --list-boots
```

This will display a list of boot sessions, each with an index (e.g. `-1` for the previous boot, `-2` for the one before that).

To see all shutdown events and their reason, run:

```shell
$ journalctl --no-pager | grep "shutting down the system"
```

If you want more details, you can check the logs leading up to a specific reboot. The following command displays the last 50 log entries immediately before the last system shutdown:

```shell
$ journalctl -b -1 -n 50 --no-pager
```

- `-b -1` – Retrieves logs from the previous boot.
- `-n 50` – Displays the last 50 log entries before that reboot.
- `--no-pager` – Prevents logs from being paginated.

### Progress, but the mystery remains

Since installing these watchdogs, my Raspberry Pi has remained accessible. It has not gone offline indefinitely. Fingers crossed it stays that way.

My logs show the software watchdog reboots the system regularly. It always reboots due to lost network connectivity.

While the watchdog is working as intended, the real mystery remains: why does the network keep failing and leave the Raspberry Pi in an unrecoverable state?

Still, this is real progress. I no longer have to climb onto the roof in freezing weather. The system recovers on its own, even when I'm away from home.
