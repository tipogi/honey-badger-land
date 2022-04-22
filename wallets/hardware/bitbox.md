## Initial Set up
In order to use the hardware wallet, first we need to hydrate (add the seed and/or passphrase) in the BitBoxApp, if not, it will throw an error the software wallets like `sparrow` and `electrum`. That steps, we describe in recovery
**IMPORTANT:** To check the wallets funds, the device has to be unlocked and in case of passpharse, it has to be added.

## Firmware
From now, I could not find any tutorial how to install from source the firmware so, we will update using the [BitBoxApp](
`https://github.com/digitalbitbox/bitbox-wallet-app/releases`). Check how to install in [[3.4.bitboxApp | BitBox manual]]

## Passphrase
If we want to use in our wallet the passphrase, we have to activate in the BitBox App. Go to `Manage Device -> Expert Settings -> Enable Passphrase` and in the application, we have agree of the steps. First click in `Learn how it works`.
![[bitbox_manage_device.png]]
Once the passphrase option is active, close the app to use that feature
![[bitbox_passphrase_active.png]]
If we forget to add the passphrase configuration, we have an option in `sparrow` that we can enable or disable the passphrase but for that we have to have the seed inside device and also created new wallet. Once we do that, in setting status bar there is an icon to toggle the passphrase option
![[toggle-passphrase.png]]
## !Recovery
Get the *seed* and *passphrase*. First, we need to add the seed in the BitBoxApp. **IMPORTANT! DO NOT ADD THE PASSPHRASE** when we are going to add the seed (hydrate), JUST add the seed. In the moment to add the passphrase, let blank (do not add any characters). The reason of that is because it might be some leak of our *public key* with the BitBox app so, just in case, just add the seed.
1.- Add the seed and after create a password when the device is locked to unlock
![[1.bitbox_restore_I.png]]
Once you restore the seed, you will get that message
![[2.bitbox_restore_II.png]]
2.- If we do not activate the passphrase option go to `manage device` module. For more info go to above section of passpharse.
Once we hydratate the seed close the bitbox application and unplug the bitbox from the computer. Now in our device, we have the seed in the secure element so, careful what you do now. Connect again our device and follow the instructions, now add the *passpharse* if we want to access to that wallet. If we want just the seed to create the wallet let blank the *passphrase* and accept
**IMPORTANT!:** All the time that we unplug the device, the passphrase is deleted from device letting just the *seed* in the secure element.
##### Electrum
3.- Go to `electrum` and *File -> New -> Create new Wallet -> Next -> Standard Wallet -> Hardware wallet -> Derivation Path* and after follow the screen options. **NEVER! ADD THE PASSPHRASE IN THE COMPUTER, ONLY IN THE HARDWARE WALLET**
![[1.electrum_new_wallet.png]]
![[2.electrum_standard_wallet.png]]
![[3.electrum_hw.png]]
![[4.electrum_derivation_path.png]]
##### Sparrow
If the device is switch off, plug and follow all the instructions of the device. If we need add the passphrase if not let blank the passphrase field and we will access to the wallet created from seed. Once we finish that and the device is unlocked:
1. Open `sparrow` and *File -> new Wallet -> Name*. The hardware wallet has to be unlocked and added the passphrase (if need it), if not is not going to recognise the device (bitbox)
2. *Connected Hardware Wallet -> Scan -> Import Keystore -> Apply*. When the left bars all of the options are blue it means that our wallet is ready to use
![[1.HW.png]]
![[2.Scan.png]]
![[wallets/hardware/img/sparrow/bitbox_hw/3.import.png]]
![[4.apply.png]]
![[5.ready.png]]
## Delete the seed
**This would be a good practise always we interact with our cold storage wallet, hydratate and after wipe seed. Like this even they steal our wallet, they will not have our seed even the seed is secure enough in the device secure element**.
Now lets go, **DO NOT OPEN THE APP, if we have the passphrase in the device**. This is just a privacy practise. If that is the case, unplug the device and plug it again. Follow the steps and let empty the passphrase(do not add any character). We advise that, in order to not leak another extended public key (even the bitbox app is connected to our node but just in case...) of the wallet created from *seed + passphrase*. Previously, we leak (or not) the extended public key when we set up our wallet created from the *seed* so, just in case, not share another wallet information (*seed + passphrase*). Now you are ready to wipe the seed.
STEPS: To let empty the HW and not keep the seed in the secure chip (good practise if our seed is cold storage), we have to go to `Manage device -> Secrets -> Factory reset device`
