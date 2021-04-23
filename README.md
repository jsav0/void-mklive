# LXD Appliance Image Creator
## Usage:
1. Make the image
```
make $( (make rootfs-all-print ; make images-all-sbc-print ) | grep -e aarch64-musl -e rpi3-musl)
```
2. Extract the platformfs or write the image to the sdcard or USB drive of your choice and boot.

Notes about this image:
- LXD is enabled
- ZFS is compiled and loaded
- new user: void
- passwords disabled for root and void
- sshd is enabled
   - logins are permitted for "root" and "void"
   - your ssh pubkeys are copied from the local /root/.ssh/id_ed25519.pub on the build server into the filesystem when the image is created
- the hostname is set to the device's serial number on boot
