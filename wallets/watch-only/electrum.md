# Electrum watch-only wallet
### Creation
**IMPORTANT:** Before create that wallet, we need to connect electrum to our node to not share any information about our wallet, in that case the extended public key. To do that go to [[3.3.electrum-wallet | Connect electrum to our electrs instance]] block. Once we set up the connection with our node, we are ready to create the *watch-only wallet*
Open in electrum previously created wallet, better if we use a wallet that is in the hardware wallet. For more info, go to `wallets -> hardware` folder in that repository. The wallet opened, go to:
`Wallet -> Information` and it will pop another window with the extended public key of the wallet. Copy selecting all the character or clicking in the copy button
![[1.extendingPublicKey.png]]
`File -> New/Restore`, add some name that it will relate the wallet
![[2.createWatchOnly.png]]
`Standard Wallet`
![[3.standard-wallet.png]]
`Use a master key`
![[4.master-key.png]]
`Copy the master Key`
![[5.paste-master-key.png]]
And our watch-only wallet is created
![[6.created.png]]
As we say, its **important** to backup that wallet and not lost all the noted tags. To backup `File -> Save backup`
