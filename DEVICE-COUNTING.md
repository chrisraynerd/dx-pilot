# Device counting in DX Pilot v0.5.0

DX Pilot helps count active participating installations. This is enabled by
default, clearly shown in web setup, and can be switched off.

## Turn counting off

Open the display's local web setup using its address and login shown on the
screen. Select **Advanced settings & privacy**, clear **Help count active Ham
Pilots**, and select **Save privacy settings**. Confirmation appears immediately.
No restart is needed. The choice survives restarts and ordinary updates; it does
not change your station, log, radio feeds or firmware-update settings.

## Data sent

About every 15–17 minutes while internet-connected, a small HTTPS check-in sends:

- A random 128-bit installation ID, retained on that installation.
- Display model: 2.8-inch CYD or 3.5-inch 035C.
- Firmware version.

The ID is randomly generated, not derived from the MAC address or callsign.
No callsign, locator, coordinates, Wi-Fi credentials, logbook, spots, operating
preferences or radio activity is included. The first attempt is delayed briefly.
A factory erase can create a new ID, so counts represent approximate participating
installations rather than people or a guaranteed number of physical boards.

## Server storage and retention

The server receives an IP to make the connection, but counting request access
logs are disabled and IP addresses are not written to the counting database.
Transient IP-based rate limiting protects the endpoint. Ordinary unrelated
website and external data-service logging is separate.

The counter stores a keyed hash of the random ID, first/last seen, model and
firmware version. Device records expire after 90 days of inactivity; per-day
records used to avoid duplicate counts expire after 31 days. Daily aggregate
totals expire after 400 days. Cleanup runs daily and on counter requests.
There is no permanent history of each check-in.

Turning counting off stops future check-ins. Previously received records expire
on that schedule; a device can remain in the approximate online count for up to
45 minutes. Aggregate information is currently available only to the project
owner behind a protected login. No public device or activity list is provided.

Questions: contact Chris through [dxpilot.co.uk](https://www.dxpilot.co.uk/).
Both supported display builds include device counting.
