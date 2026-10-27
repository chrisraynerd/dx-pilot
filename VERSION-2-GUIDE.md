# DX Pilot v0.5.3 guide

Version 0.5.3 is available for both the 2.8-inch CYD and 3.5-inch 035C, with
matching functionality and separate display/touch drivers. Both builds have been installed and checked on their supported hardware.

Wi-Fi update controls are in Web setup and Info > Sources > Updates.
See [WIFI-UPDATES.md](WIFI-UPDATES.md). Use the browser installer for a first installation; compatible future releases can then be installed over Wi-Fi.

## Import your log

In Web setup, open **My log & personalised DXCC alerts**. Choose an ADI/ADIF
export, select the station records, read the summary, then replace the saved log.
Your browser processes the full file locally. The display receives a fixed 24 KB
country/band/mode summary with separate worked and LoTW-confirmed results.
Reimport an updated export to refresh contacts and confirmations.

Choose one comparison: country overall, on band, in exact mode, or on band and
mode together. FT8 and FT4 are separate. The default basis is **LoTW confirmed**.
Paper/eQSL confirmations and records merely sent to LoTW do not count.
Missing information appears in the import warnings. A partial summary requires
explicit acceptance before log-based alerts can run. No log means no NEW alerts.

## Rarity and alerts

Rarity uses Club Log's worldwide/all-mode ranking independently of your log.
The default threshold is the top 100, adjustable from 1 to 340. Enable rarity and
the master red-alert switch to receive these alerts. Normal band/mode filters
and the additional alert-mode choices still apply. Device settings include
**DX alerts** and **Rarity/time**.

Alerts pulse red three times and remain visible for 30–600 seconds. A repeat
needs a newly received newer report within your freshness window (default five
minutes), after the chosen 3–30 minute per-country cooldown. No timer-only repeats.
An alert can be dismissed without recording a contact or confirmation.

**Info → My log & DX alerts** shows the summary, country list and recent alerts.
Clearing the log summary preserves station, Wi-Fi and display settings.

## Separate propagation and spot modes

Under **Settings > Modes**, open either **PSK propagation modes** or **DX spots
modes**. Web setup has matching independent groups. PSK defaults to All modes
on upgrade; your existing DX selection is kept. SSB-only DX no longer removes
the FT8/FT4 reception evidence used by the propagation summary and map. Alert
modes have their own controls. Save the settings to apply changes.

## Choosing your cluster

In web setup or Settings > DX cluster, leave **Default** selected or choose
**Custom** and enter a Telnet node address and port. Login options can usually
remain blank. Choose UK, Europe, Worldwide or custom reporting stations, then **Test
connection** for a clear result without saving. Save settings when you want the
choice to survive a restart. See [Choosing a DX cluster](CLUSTERS.md).

## Clock weather

The clock shows a weather symbol, Celsius temperature and a short description
for your saved grid location. See [WEATHER-CLOCK.md](WEATHER-CLOCK.md).

## Device counting

Device counting defaults to on, with a persistent opt-out in Advanced
web settings. See [DEVICE-COUNTING.md](DEVICE-COUNTING.md) for the exact data,
retention and how to switch it off.

## On-screen device status

Open **Info > Device status** for the firmware version, display model, Wi-Fi and
feed connections, imported log count, storage and free memory. Tap **Next** for
calendar download/save messages and saved-calendar ages, then **Next** again for
log/calendar file sizes. **Refresh** takes a fresh storage snapshot. Nothing on
these pages deletes logs, changes settings or restarts the device. A photo helps
support diagnose problems without needing the local web dashboard.
