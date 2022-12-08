# Ronin Dojo
RoninDojo is the one stop shop for all things bitcoin, privacy, and soveriginty. They are here to serve anyone that is ready to run a bitcoin node, take full custody of their bitcoin wallet, preserve their privacy, and live freely.

![RoninDojo](../docs/assets/ronin-dojo.png)

[Bitcoin](https://ronindojo.io/bitcoin.pdf) is defined as "peer-to-peer version of electronic cash" that you can use "without going through a financial institution", and they hope to play their part in making this a reality.

Go to [ronin wiki](https://wiki.ronindojo.io/en/home) and start discovering what you need.
- [DIY build kits](https://wiki.ronindojo.io/en/hardware#tanto-by-ronindojo-diy-build-kits): Get the hardware pieces and build the node, there are different type of single boards, *rpi4* or *rockpiPro*
- [Installtion](https://wiki.ronindojo.io/en/extras/OS-Info): Once we have the hardware, flash the SD and start running the node
- [Downloads](https://ronindojo.io/en/downloads.html)
### OS verification
Ronin OS is a manjaro image built-in to work with Ronin Dojo implementation. After download, verify the image:
```bash
gpg --verify Manjaro-ARM-RoninOS-rpi4-*.sha256
sha256sum Manjaro-ARM-RoninOS-rpi4-*.xz
# Check if we get the same hash in the file
cat Manjaro-ARM-RoninOS-rpi4-*.sha256
```
### Useful
- `IP`: If we cannot get the IP of the node, download the `angry IP scanner` from downloads page
- `User password`: Sometimes after the installation, the password of each user does not work. In that case, we can renew the password with the following command: `passwd [username]`