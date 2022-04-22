## Firmware
This is an advanced hardware wallet, first play with *trezor* and *bitbox*
**CAUTION!**: Our ColdCard model is `mk3`. Before upgrade, check if our device has a compatible version. Go to the following URL and find the latest version:
```bash
https://coldcard.com/docs/upgrade
```
Verifying the firmware's hash and signature requires PGP signature verification
```bash
# Check if the hash matches with the signature.txt
sha256sum 20...-coldcard.dfu
# Check if the signature is the right one: Import and verify
curl "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0xA3A31BAD5A2A5B10" | gpg --import
gpg --verify signatures.txt
```
Once the outputs are the correct ones, we can upgrade the device. Copy the `.dfu` file in the root path of the SD card and switch on the CC (plug it with USB but not connect to PC, better to some socket). Go in the device `Advanced > Upgrade > From MicroSD` and start the installation.