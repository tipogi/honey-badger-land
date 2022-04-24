# Wallets
- First, we need to create the wallets with the hardware wallet in order to not store in any moment the seed and passphrase outside of it. 
- After, create the watch-only wallets to not hydrate (add the seed and passphrase in the hardware wallet) always that we want to get new addresses to receive coins and to tag each UTXO.
- Finally, backup the watch only wallets because if we backup the wallets created with hardware wallets, that backup contains the private keys (even the backup is encrypted) and it might be dangerous. *I am not sure of that point so, do not trust, verify!*

More info about import backups of wallets in [estudiobitcoin.com](https://estudiobitcoin.com/etiquetar-para-mantener-nuestra-privacidad-en-bitcoin/)
Now, if we want to have some coins for daily spend, use mobile wallets.