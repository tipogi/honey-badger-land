## Download and verification
*NOTE:* If do not have samurai wallet team keys [download](https://samouraiwallet.com/pgp) before application verification.
Once we have the keys, go to [Samurai Wallet](https://samouraiwallet.com/download) and download `apk` and `asc`. To not get that output, *was not verified*, trust the key. Go to [[3.1.whirlpool-desktop | Whrilpool manual]]
```bash
$ gpg --verify sw-*.asc (gpg: WARNING: not a detached signature; file 'sw-signed-0.99.95d.apk' was NOT verified!)
$ openssl dgst -sha256 sw-signed-0.99.95d.apk
$ sha256sum sw-signed-0.99.95d.apk
```
#### TroubleShooting
These are the common problems
##### Re-Dojo the wallet
If we re-flash ronin dojo, we need to *re-dojo* the wallet.
1. Before delete the wallet, get the **seed**, `settings -> wallet -> show mnemonic` and **passphrase**, `settings -> troubleshoot -> passphrase/backup test`. Also make a backup to not lost all the tags of the wallet, `three dots -> Export Wallet Backup`
2. Delete wallet: `settings -> wallet -> Secure erase wallet`
3. Close the wallet and follow the set up steps. Choose `mainnet` network. IMPORTANT:  before add the backup connect to **Dojo** (use `Dojo Maintenance Tools` to pair the wallet)
4. Usually after that step the balance of the wallet would be 0, so follow next block

##### Missing balance
If we have problems to see our actual wallet balance we need to re-index our public keys. Usually *samurai wallet* uses *segwit wallet*(BIP84, `bc1`) in the wallets
1. Export the public key, `Settings -> Wallet -> Show zPub`
2. Open *Dojo Maintenance Tools* and `Tools -> xPub Tools`
3. Add our public key and click in `ReType`. If we do not do that step, it will scan *BIP44* derivation type not *BIP84*. 
4. Choose *BIP84* and import. This will start the re-scaning process (it might take time depending wallet past tx). If you want to check the rescanning, go to `Dojo (1) -> Logs (4) -> NodeJS (4)`
5. Once the process is finished, close the wallet and open again. Now, your funds will be available