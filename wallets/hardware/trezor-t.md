## Initial set up
Hydrate (add the seed) with **electrum** if the device does not have a seed. In **Sparrow**, we cannot hydrate the device because it throws an error if it does not contain the seed.
## Firmware
Access to [trezor github repository](`https://github.com/trezor/webwallet-data/tree/master/firmware/2`), always has to be `2` folder (in our case, Trezor T). We will use that folder also to check the hash of the new trezor firmware file.
### Preparation:
1.- Check if the `trezorctl` [library](https://pypi.org/project/trezor/) is up to date. If the version does not match or if we get some error running the second command, check [[3.3.electrum-wallet | electrum wallet manual]] 
```bash
$ trezorctl version
# In that case, we are going to update
$ pip3 install -U trezor
# Check the device connection is successful
$ trezorctl ping "ahoy!"
```
When we choose the new firmware version from the list, in the url has to be `raw` not `blob` (important)
2.- Download **trezor-xx-bitcon-only.bin**. To get the right file, select the latest firmware and in the redirected page, hover over **download** button and copy the url to after download with `wget` command
![[download.png]]
```bash
# NOT install 'blob' url. ERROR
$ wget https://github.com/trezor/webwallet-data/blob/master/firmware/2/trezor-2.4.1-bitcoinonly.bin
# YES instal 'raw' url. SUCCESS
$ wget https://github.com/trezor/webwallet-data/raw/master/firmware/2/trezor-2.4.1-bitcoinonly.bin
```
**NOTE**: As we say above, if we download from `../blob/..` url, we will get the following error:
```bash
$ Unrecognized firmware image type
```
4.- After download, go back to the list and click in the selected firmware row, the second column (our case `feat(fw): add 2.4.1 and 1.10.2 versions`). There we can check the firmware fingerprint 
4.- Set the device in bootloader mode: https://www.youtube.com/watch?v=xVBiSFTx0qQ
Slide up and down the screen and connect the trezor
5.- Install the new firmware but first check the *firmware fingerprint* as we say above. 
![[fingerprint.png]]
6.- Next, run the firmware installation command and before confirm the installation in the device, it gives as output the fingerprint hash. Check and after that confirm in the device:
```bash
# 2.4.1
$ trezorctl firmware-update -f trezor-2.4.1-bitcoinonly.bin
# Once the hash of the file and the fingerprint of the bitcoinonly hash are the same, press in the device 'Yes'

```
## Passphrase
If we want to add in trezor the passphrase there are two options:
- In **sparrow** we have an option to disable the passphare. Once we add a wallet in the application, at the bottom we have usb icon. If we navigate through that, we have toggle option. If it is active, it will disable and viceversa
![[toggle-passphrase.png]]
- In contrast, in **electrum**, we need to do that when we are creating new wallet. `File -> New`... and in the window that says to set a label for the device, we have a button that it says *show expert settings*. So, the proccess is click in `Show expert settings -> Enable passphrases`. If we do not check `Enable passphrases` until we wipe the seed from the device, we are not going to be able to add the passphrase in **electrum**. If that happens, you can go to sparrow and follow the above steps.
![[enable-passphrase.png]]
## !Recovery
Above, we say that it is not possible to hydrate with **sparrow** so, we will do with **electrum**:
`File -> New -> Name -> Standard Wallet -> Use a hardware device -> Initialise device -> Passphrase -> Derivation Path`
![[1.new_wallet.png]]
![[2.standard_wallet.png]]
![[3.hw_device.png]]
![[4.select_device.png]]
![[5.initialise_device.png]]
![[6.configuration.png]]
**WARNING:** Never add the passphrase in the computer, always in the HW
![[7.passphrase.png]]
![[8.derivation_path.png]]
##### Sparrow
Now, if we want to add our wallet in `sparrow` wallet (check [[bitbox | BitBox manual]])
`File -> New Wallet -> Connected hardware Wallet -> Import -> Apply`. The only step that it changes is the 3rd one which is `connected HW`
![[citadel ????/wallets/hardware/img/sparrow/trezor_hw/3.import.png]]
## Delete the seed
**This is a MUST in that HW because it can extract our seed in 15min**. Once we interact with the coins of the cold wallet, wipe the device seed. To clear the seed and not keep the seed in the secure chip, run this commands in the terminal (the device has to be unlocked with the PIN)
```bash
# Make sure if the computer detects the device
$ trezorctl ping "ahoy!"
# Clear the seed from the device
$ trezorctl wipe-device
```