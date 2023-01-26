# Backgrond
When we want to store our honey badger coins, first we need to create a **seed**. There are two options. Create using a HW or flipping a coin. The second one is more secure because the coin gives the entropy to the seed, not the HW random generator script. Here some tutorials, how to do that:

- Do you trust your seed? Don’t!, [here](https://estudiobitcoin.com/do-you-trust-your-seed-dont-generate-it-yourself/)
- Crear wallet sin necesidad de hardware wallet, [here](https://estudiobitcoin.com/guia-definitiva-para-crear-una-wallet-sin-necesidad-de-hardware-wallet-metodo-ii/)

## Hardware Wallets

Once we have our seed, we can receive our first coins in the wallet. The seed always has to be in the wallet no matter what, **it cannot have contact with the outside world (internet)**. So the only way to do that is using hardware wallets.
It is recommended to delete the seed, once you we create the backup of the seed. More info [here](https://bushido.guide/explorer/bitcoin/wallets/tools)

## Watch-only wallets

To avoid to connect all the time the hardware wallet to some device, it is recommended to create [[citadel 🏔/wallets/watch-only/readme|watch only wallets]]. With that we will avoid to _hydrate_ (add the seed and passphrase in the hardware wallet) each time that we want to receive the coins. The hydration only happens, if we delete the seed from the hardware wallet. Important in that wallets to tag each address. More info [here](https://estudiobitcoin.com/etiquetar-para-mantener-nuestra-privacidad-en-bitcoin/)
