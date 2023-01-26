# Electrum connected to Ronin
If you want electrum to appear in a Linux app launcher ("start menu" or cmd + space), we need to configure the `xxxx.desktop` file.
### Get electrum onion address
Access to the *ronin dojo node* through [[citadel 🏔/nodes/readme#SSH | SSH]], go to `Credentials (5) -> Electrs (3)` and we will get the _electrum server onion address_
### Create .desktop file
Now create the file in __our local machine__ pasting the below snippet in the file. It could be a case that this file is already created but the procedure is the same. You can give what ever name to the file but always it has to have `.desktop` extension. In our case, we call the file with the name of the application: `electrum.desktop`

```bash
vim /usr/share/applications/electrum.desktop
```

**NOTE:** Replace in the file `onion_address.onion` with our _electrum server onion address_ (we get running above command) and the _electrum server onion address_  has to be without `http`
```bash
[Desktop Entry]
Comment=Lightweight Bitcoin Client connected through TOR
Exec=sh -c "PATH=\"\\$HOME/.local/bin:\\$PATH\"; electrum --oneserver --server onion_address.onion:50001:t --proxy socks5:127.0.0.1:9050"
GenericName[en_US]=Bitcoin Wallet
GenericName=Bitcoin Wallet
Icon=electrum.icon
Name[en_US]=Electrum Wallet
Name=Electrum Wallet
Categories=Finance;Network;
StartupNotify=true
StartupWMClass=electrum
Terminal=false
Type=Application
MimeType=x-scheme-handler/bitcoin;
Actions=Testnet;

X-Desktop-File-Install-Version=0.26

[Desktop Action Testnet]
Exec=sh -c "PATH=\"\\$HOME/.local/bin:\\$PATH\"; electrum --testnet %u"
Name=Testnet mode
```

### Install .desktop file
Once the _electrum.desktop_ file is created, now we need to create the launcher of electrum application.
```bash
sudo desktop-file-install electrum.desktop
```
The launcher is created and we can open the application from the start menu

