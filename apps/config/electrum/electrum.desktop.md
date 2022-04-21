If you want electrum to appear in a Linux app launcher ("start menu" or cmd + space), install this by doing:
```bash
# sudo desktop-file-install electrum.desktop
```

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