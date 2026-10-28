# DX Pilot

For JTDX desktop software, see [JTDX Companion](https://github.com/chrisraynerd/jtdx-companion).

Display website: [www.dxpilot.co.uk](https://www.dxpilot.co.uk/). Latest firmware: **0.5.4** for both supported display sizes.

**An HF propagation, DX spotting and shack clock display for 2.8-inch CYD and 3.5-inch ESP32-3248S035C touchscreens.**

By **G1CEC - Chris Raynerd**. Copyright 2026.

## Download and install

Use the [browser installer](https://www.dxpilot.co.uk/#install) and choose your
screen, or select the matching package from [Releases](https://github.com/chrisraynerd/dx-pilot/releases):

| Display | Firmware package | Controllers |
| --- | --- | --- |
| 2.8-inch CYD, tested standard and Diymore boards | [DX-Pilot-v0.5.4-firmware.zip](https://github.com/chrisraynerd/dx-pilot/releases/download/v0.5.4/DX-Pilot-v0.5.4-firmware.zip) | ILI9341 / ILI9341V or supported ST7789, XPT2046 touch; 320 x 240 |
| 3.5-inch ESP32-3248S035C | [DX-Pilot-v0.5.4-cyd35c-firmware.zip](https://github.com/chrisraynerd/dx-pilot/releases/download/v0.5.4/DX-Pilot-v0.5.4-cyd35c-firmware.zip) | ST7796, GT911 capacitive touch; 480 x 320 |

Both display sizes have **v0.5.4 functionality**, built from the same application
source with separate display/touch profiles. The
3.5-inch build fills the screen width and uses physical-size lettering. Both
need 4 MB ESP32 flash. The 035R resistive model and other controller/wiring
variants need different firmware. Read [INSTALL.md](INSTALL.md) before flashing.

The website installer follows the newest stable firmware for each board, checked
every five minutes. Drafts and prereleases stay out of the installer. 

Choose a firmware ZIP above rather than GitHub's automatic "Source code" archive;
that archive contains this documentation repository, not the application project.

## What it shows

- PSK Propagation from your chosen location: recent nearby receiver reports by HF band.
- Six-row DX spots with frequency, prominent countries, coloured modes and tap-to-open details.
- Observed propagation paths with day/night shading and the Sun's overhead position.
- UTC/local clock, sunrise/sunset, and selected major contests now/next.
- HamQSL HF day/night outlook with SFI and K.
- Info menu with DXpedition and contest calendars, device status and source/licence credits.
- On-device and authenticated local web settings; independent page durations.
- Independent PSK propagation and DX spot mode selections; UK, Europe or worldwide cluster reporters.

It needs **2.4 GHz Wi-Fi and internet access**, but no radio/CAT connection or
permanently connected computer. HF bands are 80, 40, 30, 20, 17, 15, 12 and 10 m.
Nearby PSK reception is evidence from those receivers, not a guarantee at your
antenna. A cluster spot is an operator's report. No reports does not mean closed.

## First use and controls

Fresh installations have blank station fields. On 2.8-inch CYDs, calibrate touch;
on the capacitive 035C, use a bare finger and no calibration is needed. Enter your
callsign, home Maidenhead locator, place and Wi-Fi in Settings. You can also join
DX-Pilot-Setup using the password shown on the device, open http://192.168.4.1,
and sign in as `ham` using that same device password. Saved profiles remain on
the device during normal updates. Choose your local time zone and reporting
station filters; the initial time zone and cluster filter are UK-oriented.

On-device Wi-Fi settings include Show/Hide for checking and correcting the existing password. Tap Done, Back, then Save settings & restart to apply changes.

Tap the bottom-left clock for Settings; tap Info for calendars. Tap a DX row for
details and Back to return. Tap a page header/blank area to advance. Hold roughly
one second to pause/resume, or four seconds for Settings. Each page can have its
own duration. Browsing Info or details pauses automatic rotation temporarily.

## Use, sharing and source

You may build your own device and use the firmware noncommercially under
[LICENSE.md](LICENSE.md). **Commercial use of DX Pilot's application code,
including selling devices running it, requires separate permission.** Third-party
rights remain intact; see [NOTICE.md](NOTICE.md).

This is the public **firmware and documentation** repository. The editable DX
Pilot application is developed privately. Release assets include the required
library sources/notices and application object files/instructions for LGPL
relinking. Those are not an editable DX Pilot application project.

DX Pilot includes browser ADIF import, worked/LoTW-confirmed DXCC comparisons,
independent Club Log rarity alerts, custom Telnet clusters, Wi-Fi firmware updates
and a home-weather clock. See [the user guide](VERSION-2-GUIDE.md).
Both builds include these features. Both hardware builds have been installed and checked over Wi-Fi. Rollback and restoration were also tested on the 3.5-inch board.
For support, open **Info > Device status**. Next shows calendar errors and then
storage file sizes and restart details. Refresh rechecks storage; Retry feeds
on the calendar page requests another download. These pages can be photographed
without opening the web dashboard.

Report bugs through Issues with the firmware version and board details. Do not
attach Wi-Fi passwords, full flash backups, private logs or device login details.

Data/service credits are in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

## Device counting (v0.5.0)

Device counting is enabled by default. It sends only a random installation ID,
display model and firmware version to raynerd.co.uk about every 15 minutes.
No callsign, location, logbook or radio activity is sent. Disable it in
**Web setup > Advanced settings & privacy**, without a restart or loss of features.
See [DEVICE-COUNTING.md](DEVICE-COUNTING.md) for collection and retention details.
