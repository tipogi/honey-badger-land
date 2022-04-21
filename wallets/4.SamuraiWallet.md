## Download and verification
Go to [Samurai Wallet](https://samouraiwallet.com/download) and download `apk` and `asc`. To not get that output, *was not verified*, trust the key. Go to [[3.1.whirlpool-desktop | Whrilpool manual]]
```bash
$ gpg --verify sw-*.asc (gpg: WARNING: not a detached signature; file 'sw-signed-0.99.95d.apk' was NOT verified!)
$ openssl dgst -sha256 sw-signed-0.99.95d.apk
$ sha256sum sw-signed-0.99.95d.apk
```