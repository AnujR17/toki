# Recover the prototype baseline

Known baseline: [a7c8d36](https://github.com/AnujR17/toki/commit/a7c8d36506d11dc6f0e7ee06561cca6be3bd666d),
app 1.1.0 (Android versionCode 2), firmware 3.0.6, protocol 3.

Inspect the baseline on a separate branch after committing or stashing local changes:

```sh
git switch -c inspect-baseline a7c8d36506d11dc6f0e7ee06561cca6be3bd666d
```

For a shared branch, revert later change commits instead of resetting main.
The earlier development workspace retained build artifacts; those artifacts and
its local recovery tags are not included in this repository. Rebuild from this
baseline or use a separately preserved, verified binary.

The recorded firmware application binary was 1,782,928 bytes, with SHA-256
`f3874ea537b23321c3a7ffb480fbcaae889aeb72f1573725a7c5045f9183e520`.
Retain the matching partition layout when rebuilding for the existing device.

To restore firmware, pause the task, enable Wi-Fi update, connect a nearby
phone or laptop to Toki's Wi-Fi, open the authenticated upload page, and upload
the application `.bin`. Keep USB recovery available. Do not upload a bootloader
or partition binary for routine OTA. A cloud workspace cannot reach the private
access point without a nearby connection.

A Git revert alone does not downgrade an installed app or device firmware.
The imported app uses `com.anujr17.toki`; builds with this identifier install as
a separate app from builds with another identifier. Export valuable task data
before changing installations. Firmware recovery does not restore previous NVS
contents; keep protocol-3 queue and storage formats compatible.
