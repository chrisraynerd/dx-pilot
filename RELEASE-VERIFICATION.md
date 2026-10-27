# v0.5.3 verification — 27 October 2026

Both hardware profiles use the same application source. The owner confirmed
frequency readability, spot details and the independent PSK/DX mode controls
and Back navigation on both physical display sizes. Live unlabelled phone-band
cluster reports were recovered as estimated SSB on each board. Europe reporter
selection was checked against live reports and Country Files DXCC membership.

Both clean 0.5.3 images were installed over Wi-Fi and accepted by startup checks.
Each had PSK modes All, DX modes SSB, 80 cached PSK reports and 80 mapped paths,
with Wi-Fi, PSK and cluster connected. Checked station/Wi-Fi/touch/page settings
and imported-log metadata were preserved. The 3.5-inch log retains 11,105 contacts;
the 2.8-inch baseline has no imported log.

Actual web controls were tested for independent checkbox state, rejection of an
empty PSK or DX selection, and save/restart persistence. Core host regressions
cover separate source-mode selection, explicit-mode precedence, unlabelled phone
inference, digital/image/CW ambiguity, timestamps, Europe membership and existing
fragmented login/Telnet behavior. Quiet live feeds do not prove every node format
or traffic volume; historical spots are not fetched automatically.

Final application images:

- 2.8-inch: 1,731,840 bytes; SHA-256 `57bde93241307b4930add9cb1483aacbc071ea677761400483fa35fd147a8bf2`.
- 3.5-inch: 1,793,616 bytes; SHA-256 `ddb61ca94f43b189dbce3fde2691ad3fe1f84a6d3dfd60c03bfd13256433800e`.

All 41 copied source/header inputs match final source for each profile. Both
firmware packages pass installer and image identity/checksum validation. All six
firmware/relink/library archives pass integrity and private-file checks. Relinking
supplied objects reproduces both exact images. Third-party sources, notices and
LGPL relinking materials accompany the firmware; editable application source,
private history, device snapshots and logs remain private.
