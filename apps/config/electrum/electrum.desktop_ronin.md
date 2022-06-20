# Electrum Ronin dojo
When we get the electrs onion address copy without `http`
```bash
# If you want Electrum to appear in a Linux app launcher ("start menu"), install this by doing:
# sudo desktop-file-install electrum.desktop

[Desktop Entry]
Comment=Lightweight Bitcoin Client connected through TOR
Exec=sh -c "PATH=\"\\$HOME/.local/bin:\\$PATH\"; electrum --oneserver --server onion_address.onion:50001:t --proxy socks5:127.0.0.1:9050"
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