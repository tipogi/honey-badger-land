# Electrum connected to Raspibolt
If you want electrum to appear in a Linux app launcher ("start menu" or cmd + space), we need to configure the `xxxx.desktop` file.

### Renew electrum onion address
The _electrum server onion addres_, we will get accessing *raspibolt* node through [[citadel 🏔/nodes/readme#SSH | SSH]].
The _electrum server onion address_ (`xxxx.onion`) might be outdated, so we have to check if still is healthy. We can go understand better in [raspibolt](https://raspibolt.org/guide/bitcoin/electrum-server.html#remote-access-over-tor-optional) documentation. 
If we want to restart the hostname (_electrum server onion address_), delete the folder (or renamed) and restart `tor` service
```bash
// #DELETE the folder
rm -rf /var/lib/tor/hidden_service_electrs
// #RENAME the folder
mv /var/lib/tor/hidden_service_electrs /var/lib/tor/hidden_service_electrs_old
// # RESTART the tor service
sudo systemctl restart tor
```

### Create .desktop file
Now that we have the onion address, it is time to create the launcher in our __local machine__. Once we have the electrum service able to run under the tor network, get the hostname that after we will add in the `.desktop` file. This command will output the _electrum server onion address_
```bash
sudo cat /var/lib/tor/hidden_service_electrs/hostname
```
Now create the file and paste the below snippet in the file. It could be a case that this file is already created but the procedure is the same. You can give what ever name to the file but always it has to have `.desktop` extension. In our case, we call the file with the name of the application: `electrum.desktop`
```bash
vim /usr/share/applications/electrum.desktop
```
__NOTE:__ Replace in the file `onion_address.onion` with our _electrum server onion address_ (we get running above command)
```bash
[Desktop Entry]
Comment=Lightweight Bitcoin Client connected through TOR
Exec=sh -c "PATH=\"\\$HOME/.local/bin:\\$PATH\"; electrum --oneserver --server onion_address.onion:50002:s --proxy socks5:127.0.0.1:9050"
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

