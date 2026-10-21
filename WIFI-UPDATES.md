# DX Pilot Wi-Fi updates

Both supported display sizes can check for updates and install compatible firmware over Wi-Fi.

## Check and install

Open **Firmware updates & previous versions** in the device's local web setup, or **Info > About > Updates** on the display. Hourly checking is enabled by default and can be switched off. **Check now** shows the result beside the button. Finding an update never installs it automatically: confirm **Yes, install** when ready.

The display verifies the firmware for its hardware model, version, checksum and saved-data format before installing. It shows progress and restarts. Keep power connected during installation. Saved station details, Wi-Fi, touch calibration, page timings and imported log summary are retained.

## Previous versions and recovery

Public release history starts at **0.5.0**. As compatible future releases become available, the update page can offer earlier releases for the selected display. **Restore previous firmware** can also use the other verified application slot without downloading, when a compatible previous image is present.

The browser can upload an application **.bin** file. ZIP archives, full-device images, firmware for another screen and incompatible data formats are rejected. The bootloader supports recovery if a new application fails its startup checks. USB installation remains the recovery route if neither application slot can run.

Installers, downloads and setup instructions are at [www.dxpilot.co.uk](https://www.dxpilot.co.uk/). Wi-Fi updates use the same published firmware as the downloads. Application source is private; release packages include the required third-party notices, corresponding sources and relinking materials.
