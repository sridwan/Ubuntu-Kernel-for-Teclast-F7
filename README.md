# Ubuntu-Kernel-for-Teclast-F7
Kernel with working touchpad for Teclast F7 / F6, Jumper EZBook, and other chinese laptops with similar touchpad.
Should work with any flavour of Ubuntu.

## Latest Patched Kernel Version
[4.15.0-29](https://files.fm/u/q7spbhat#_)

Please contact me if you have a newer version, I'll put it here with proper credit.

## How to install:
1. Install Ubuntu/Lubuntu 18.04 (create bootable usb using etcher)
2. [Download](https://files.fm/u/q7spbhat#_) kernel files to an empty directory
3. If your current kernel is the same version, then you have to remove them first
   ```
    sudo apt remove linux-image-$(uname -r)-generic linux-headers-$(uname -r)-generic linux-cloud-tools-$(uname -r) linux-modules-extra-$(uname -r)-generic linux-tools-$(uname -r) linux-cloud-tools-$(uname -r)-generic linux-headers-generic linux-image-generic linux-tools-$(uname -r)-generic linux-generic linux-signed-generic
   ```
4. Install the patched kernel
   ```
   sudo dpkg -i linux\*.deb
   ```
5. If the system complain about unmet dependencies / some other error, do
   ```
   sudo apt --fix-broken install
   ```
   and do step 4 again
6. Now it's time to update grub and reboot
   ```
   sudo update-grub
   sudo systemctl reboot
   ```
7. Enjoy your working touchpad.

## Older kernel version
- [4.15.0-24](https://gitlab.com/chenlevy/teclast-f7-touchpad-fix) by Chen Rotem Levy (chenlevy)
- [4.15.0-20](https://github.com/pokulan/Ubuntu-Kernel-4.15.0-20-for-Teclast-F7) by Wojciech Zomkowski (pokulan)

## Compiling your own kernel
I use this guide to compile mine:
[http://strangequark.tk/index.php/blog/20180423_teclastf7linux](http://strangequark.tk/index.php/blog/20180423_teclastf7linux)
