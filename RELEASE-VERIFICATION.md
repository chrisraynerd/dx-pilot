# v0.5.2 verification — 25 October 2026

Both supported hardware profiles use the same application source. Private development images were installed and checked on both physical boards. The owner confirmed restart diagnostics and navigation are readable and working on each size.

Three consecutive calendar refreshes passed on each display after the final buffer correction: no restarts, no secure-connection errors, no leftover download files, and preserved settings/log metadata. The 3.5-inch board retained both 24,576-byte log slots and had 40 KB free storage; the 2.8-inch baseline had no imported log.

Host tests cover temporary-file cleanup boundaries, storage reserve and overflow checks, and restart-snapshot validation. Short checks cannot establish that all possible restart causes are resolved.

Final clean 0.5.2 images were then installed over Wi-Fi on both boards and accepted by startup checks. Three further consecutive calendar refreshes passed on EACH clean release image: both calendars OK, uptime increasing, no temporary files, unchanged settings/log metadata and log-slot sizes.

- 2.8-inch application: 1,727,808 bytes; SHA-256 `474da3402072b40565ba401c7065194c633ab22dc2d2e51b4aa9f2c9ee931f80`.
- 3.5-inch application: 1,789,632 bytes; SHA-256 `9696cd6535c8a22c6ed9938f5a9be9779a92f1bbe663fe69ae2e3e4e2166ab94`.

All 40 copied source/header inputs match the final source for each profile. The calendar policy host test and four OTA catalogue tests pass. All six firmware/relink/library archives pass integrity and private-file checks; relinking supplied objects reproduces each exact firmware image. All ten draft assets were uploaded with matching GitHub SHA-256 digests.

The application source, private history, device snapshots and logs are not included in the public repository or packages.
