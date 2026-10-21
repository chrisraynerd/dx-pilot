# Weather on the DX Pilot clock

The clock includes a weather panel to the right of the main
clock. It shows a simple weather symbol, rounded Celsius temperature and a short
condition such as Light rain or Overcast. Clear weather uses a sun or moon.
Seconds sit beneath the right edge of the large hours/minutes rather than
floating farther to the right. UTC/local time, date, sunrise/sunset and the
optional major-contest panel remain available. Both clock layouts use the panel.

Weather uses the centre of the station's saved Maidenhead grid locator. The
location name is still shown in the heading; no browser location permission or
additional account/API key is required. Changing the station grid changes the
weather location after saving and restarting.

The source is [Open-Meteo](https://open-meteo.com/), using its
[current-weather API](https://open-meteo.com/en/docs). These are model-derived
current conditions, not measurements from a sensor at the house. Data attribution:
Open-Meteo, [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Provider
attribution is shown on the clock, Info > Sources and web setup. The API's
[non-commercial terms](https://open-meteo.com/en/terms) apply to the public service;
this integration does not incorporate the service's application source code.

Successful requests refresh every 30 minutes. Failed requests retry after
15 minutes. Requests use verified HTTPS and share the existing network-memory
guard with other downloads. Cluster connection tests and firmware operations
have priority. Weather is independent of propagation and DXCC alerts.

A small saved cache binds the grid and response in one committed value, preventing
a partial cache update from associating the wrong location with a response.
It survives normal restarts and application updates. The saved retry time avoids
repeated requests during development restarts. A changed grid ignores the previous
location's cache. Existing logs, station/Wi-Fi settings and calibration are retained.

Readings older than 90 minutes are muted and marked Cached weather. Beyond six
hours, or if data fails validation, the clock shows an unavailable symbol and
no temperature unless another valid reading remains. Missing temperature, invalid
units/codes/times and incomplete JSON never become a false zero-degree reading.
Weather status is also available in the readable web device-status panel.

Available in both v0.5.0 hardware builds, using the same clock/weather code.
The 2.8-inch layout and weather fetching were physically checked. The latest
035C build is compile/package verified; physical checks of its new features
remain pending.
