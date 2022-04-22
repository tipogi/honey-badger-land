# Sparrow watch-only wallet
### Creation
**IMPORTANT:** Before create that wallet, we need to connect sparrow to our node to not share any information about our wallet, in that case the extended public key. To do that go to [[3.2.sparrow-wallet| Connect to electrs]] block. Once we set up the connection with our node, we are ready to create the *watch-only wallet*
Open in sparrow previously created wallet, better if we use a wallet that is in the hardware wallet. For more info, go to `wallets -> hardware` folder in that repository. The wallet opened, go to:
`Settings -> copy zPub`, in that case we copy segwit native public extended key but if you want another wallet type, you have to choose `xPub` or `yPub`
![[copyKey.png]]
`File -> New Wallet -> xPub / Watch Only Wallet`
![[watch-only-wallet.png]]
Now add the `derivation path`, in our case is native segwit, m/84'/0'/0', and the `zPub`
![[details.png]]
When the wallet is created, all the options will be blue
![[created.png]]
**IMPORTAT:** Create a backup to save all the noted tags and not lost the track of each coin.
`File -> Export Wallet... -> Sparrow` and save in some secure place
![[export.png]]