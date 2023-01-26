# Scansnap firmware

Please use [this](https://github.com/stevleibelt/general_vendor_products/tree/master/fujitsu/scansnap_s1300i) page for latest and up-to-date information.

## Old and outdated readme

The following is a quick and dirty way to get my Scansnap S1300 working on [Ubuntu][u], [Xubuntu][x], or [Elementary OS][e]. (This could possibly work on other Debian based linux too.)

### Installation on Debian

1. Download firmware:

        git clone https://github.com/ckunte/scansnap-firmware.git

2. Run the following commands in a Terminal

        sudo mkdir -p /usr/share/sane/epjitsu
        sudo cp ~/Downloads/scansnap-firmware/* /usr/share/sane/epjitsu/.
        sudo cpan upgrade sane
        sudo apt-get install libsane-dev
        
3. Logout, and then re-login. Try [Simple Scan][ss], and the scanner should work.

[u]: http://www.ubuntu.com/
[x]: http://xubuntu.org/
[e]: http://elementary.io/ "elementary OS"
[ss]: https://launchpad.net/simple-scan "Simple Scanning Utility."

### Installation on Arch Linux

1. Prepare System

```
sudo su
#install needed software
pacman -S sane
#optional
#pacman -S xsane
#pacman -S simple-scan

#add usb device to know sane configuration
echo “usb 0x04c5 0x1155” >> /etc/sane.d/fujitsu.conf
exit
```

2. Download firmware

```
sudo su
cd /usr/share/sane/epjitsu/
wget https://github.com/ckunte/scansnap-firmware/raw/master/1300i_0D12.nal
exit
```

3. Use it

Try [Simple Scan][ss], and the scanner should work.
Read '/etc/sane.d/epjitsu.conf', if needed.
