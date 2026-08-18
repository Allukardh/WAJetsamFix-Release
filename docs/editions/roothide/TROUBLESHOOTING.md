# RootHide troubleshooting

## Settings panel or icon is missing

1. Confirm that RootHide Patcher was used on the downloaded package.
2. Reinstall the patched package through Sileo.
3. Perform a Userspace Reboot.
4. Reopen Settings.

## Changes are not active

Confirm the selected profile in the WAJetsamFix panel and perform the requested Userspace Reboot. The calibration assistant recommends a profile but never applies it automatically.

## Integrity check fails

Delete the downloaded file and obtain it again from the [official v0.8.0 release](https://github.com/Allukardh/WAJetsamFix-Release/releases/tag/v0.8.0). Do not install a package whose SHA-256 differs from [CHECKSUMS.txt](../../../CHECKSUMS.txt).

If the problem remains, read [support](../../../SUPPORT.md) before reporting it.
