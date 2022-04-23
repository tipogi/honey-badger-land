If you want electrum to appear in a Linux app launcher ("start menu" or cmd + space), install this by doing, but first we need to add the xxxx.desktop file in the right path
```bash
# sudo desktop-file-install electrum.desktop
```
The onion service address (xxxx.onion) might be outdated, so we have to check in proper path, in my case, we can get from *raspibolt* `/var/lib/tor/electrs_service/hostname` or from *ronin dojo* `Credentials (5) -> Electrs (3)`
If we want to restart the hostname, delete the folder (or renamed) and restart `tor` service
```bash
sudo systemctl restart tor
```
Now update the onion address and add `electrum.desktop` in `/usr/share/applications`
```bash
[Desktop Entry]
Comment=Lightweight Bitcoin Client connected through TOR
Exec=sh -c "PATH=\"\\$HOME/.local/bin:\\$PATH\"; electrum --oneserver --server 5lqeiwxhvec332cwhspcvasj3of3gk3brn5ldiotivwnei3zyrjxc5yd.onion:50002:s --proxy socks5:127.0.0.1:9050"
GenericName[en_US]=Bitcoin Wallet
GenericName=Bitcoin Wallet
Icon=electrum
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