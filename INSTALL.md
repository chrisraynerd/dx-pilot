# Installing DX Pilot

## Supported hardware

Choose the firmware for your board. Both display sizes are v0.5.4 with matching functionality. Choose the correct hardware package.

- **2.8-inch CYD**, tested standard and Diymore ESP32-32E boards: ILI9341/ILI9341V or supported ST7789 LCD (automatically detected),
  XPT2046 resistive touch, landscape 320 x 240. Use DX-Pilot-v0.5.4-firmware.zip.
- **3.5-inch ESP32-3248S035C**: ST7796 LCD, GT911 capacitive touch, landscape
  480 x 320. Use DX-Pilot-v0.5.4-cyd35c-firmware.zip.

- **3.5-inch ESP32-32E resistive**, tested ST7796 / XPT2046 shared-SPI board: landscape
  480 x 320. Use DX-Pilot-v0.5.4-cyd35r-firmware.zip. This is a different firmware
  from the 035C capacitive build; it asks for three touch-calibration taps.

All supported models need 4 MB ESP32 flash. USB must support data as well as power.
The 2.8-inch pin assignments are LCD CS15/DC2/SCK14/MOSI13/MISO12/backlight21; touch
CS33/SCK25/MOSI32/MISO39. No additional wiring is needed on this supported board.
The tested 3.5-inch resistive board uses LCD CS15/DC2/SCK14/MOSI13/MISO12/backlight27;
XPT2046 touch shares SPI pins 14/13/12 with touch CS33. ESP32-32E names the processor
module, so check the screen, touch and wiring rather than assuming every board matches.
No VHF functions or CAT connection are included.

## Windows flashing

1. Install Python 3 and, if Windows needs it, the board vendor's CH340 USB driver.
2. Download and extract the firmware ZIP for your screen from Releases. Keep each board's files in its own folder.
3. In a terminal install the uploader: `py -m pip install esptool==5.3.1`.
4. Find the board's COM port in Windows Device Manager. Close software using it.
5. In PowerShell, from the extracted folder, run `./Flash-DxPilot.ps1 -Port COM6`,
   replacing COM6 with your board's port. Use your normal PowerShell script policy;
   alternatively run the manual command below.

The script checks the four firmware files against SHA256SUMS before writing.
It does not write an NVS/settings image or a filesystem image and does not erase
the whole flash. On an existing DX Pilot board the saved profile/calibration
are retained. If replacing unrelated firmware, keep a private backup first.

## Manual flashing / Linux / macOS

Install Python and esptool 5.3.1, then use the correct serial port:

```text
python -m esptool --chip esp32 --port YOUR_PORT --baud 460800 --before default-reset --after hard-reset write-flash --flash-mode dio --flash-freq 80m --flash-size 4MB 0x1000 bootloader.bin 0x8000 partitions.bin 0xe000 boot_app0.bin 0x10000 dx-pilot.bin
```

Do not substitute the application binary at address zero. Do not use a full
device backup as a public firmware image. If connecting fails, follow the board
vendor's BOOT/RESET procedure and retry, or reduce the baud rate to 115200.

## First start

The DX Pilot title appears briefly. A new 2.8-inch or 3.5-inch resistive board asks for three touch
targets; tap and release each one. The 3.5-inch 035C uses capacitive factory
coordinates: use a bare finger and skip calibration. Enter your station and
Wi-Fi in Settings and Save.
On the Wi-Fi page or password keyboard, tap Show to check the password.
Editing starts with the existing value; tap Done, Back, then Save settings &
restart to apply corrections. Calls, locator and place are blank on fresh installations. UK time zone and UK
cluster reporting prefixes are initial defaults; change them for your location.
The on-device Web setup page gives the address and device-specific login.

Let the board connect and accumulate live reports. Stored schedules and outlook
may be absent until their first successful downloads. No reports is not a closed
band. The clock obtains internet time. The PC may then be disconnected.

Settings > Reset can prepare another profile; profile reset retains Wi-Fi and
touch calibration, while Reset everything also clears Wi-Fi when saved. A saved
reset is deliberate; normal firmware updating does not reset your station.

## Device counting in v0.5.0

Enabled by default: a random installation ID, board model and firmware version
are sent to raynerd.co.uk about every 15 minutes to count active installations.
No callsign, location, logbook or radio activity is sent. In **Web setup > Advanced
settings & privacy**, clear **Help count active DX Pilots** and save to stop
check-ins immediately, without a restart. Your choice survives normal updates.
Records expire after 90 inactive days; daily de-duplication records after 31 days;
aggregate totals after 400 days. See the full collection/storage details at
https://github.com/chrisraynerd/dx-pilot/blob/main/DEVICE-COUNTING.md .
