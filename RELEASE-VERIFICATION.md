# DX Pilot 0.5.0 verification — 21 October 2026

Both hardware profiles were built from the same 37 matching source/header files and version0.5.0. Both were installed over Wi-Fi. Station, Wi-Fi, touch, page timing, log summary, LoTW/alert options and counting preference compared unchanged with private pre-update snapshots. Startup tests accepted both images; PSK and cluster connections recovered. The owner confirmed the new splash, credit, pages and touch on both screens.

The 3.5-inch board was additionally rolled back and restored, preserving settings throughout. Legacy image markers, schema2 and established firmware URL paths are intentionally unchanged so installed devices can update and roll back.

Both original-object relinks reproduce the installed firmware byte for byte. Both also link successfully using separately rebuilt matching core/library objects. Public packages use an explicit allowlist and contain no editable application source, credentials, device backup or personal log.

Publisher integration tests on Linux cover old/new package names, both boards, immutable previous downloads, checksums and interrupted activation. Firmware browser, status, counter and OTA catalog/policy tests passed.

| Display | Application bytes | SHA-256 |
| --- | ---: | --- |
| 2.8-inch | 1714688 | 9947a4bfa59dd79fd033a9f95628e606857a2586772dfc7f2e548fad226f59d3 |
| 3.5-inch035C | 1776448 | df65ba25218bfaadadd44024cec8d50dd48f027bc48aeffc6c76151a84fa8a83 |

