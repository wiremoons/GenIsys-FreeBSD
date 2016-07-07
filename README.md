
# GenIsys-FreeBSD


## Purpose

This repo contains a shell script called `Install-FreeBSD-10.3` that I use to setup a fresh [FreeBSD](https://github.com/freebsd) installation.

It was written for FreeBSD 10.3, and it sets up some initial programs and configurations that suit my purposes. It is tuned for my own use - but I have made the repo public, just in case it is useful to others also. I am a recent user of FreeBSD, so I do not claim an *best practice* with my script - so use at your own risk!

The script is used on my computers that generally have: UEFI boot, ZFS root filesystem, are 64bit desktop PCs, and an NVidia graphics card. This will therefore create a bias towards what software I choose to install with this script.

The script needs to be run as root, and performs the following actions:

1. Snapshots the ZFS (can be bypassed);
2. Updates the binary packagment tools;
3. Install the following packages: `mksh` `nano` `avahi nss_mdns` `git` `curl` `rsync` `screen` `cmdwatch` `vim` `mp4v2` `tree` `pv` `beadm` `aspell` `en-aspell` `p7zip`;
4. Offers to install Nvidia drivers, Lumina window manager, Chromium, vlc, and Xorg
5. Update system configuration files such as: `rc.conf`, `loader.conf`, and `sysctl.conf`
6. Clone this Git repo to allow further setup using the script: `setup-home` to be run by the user account after a reboot


## How It Is Used

The basic process I use with this repo is oputlined below. This would be done following a successful install of FreeBSD 10.3, and after the system has been rebooted following the install. Login to your user account and follow the process below. The high-level process steps are:

1. login to your normal user account
2. download the setup script using curl
3. switch to root user
4. run the script to setup and configure the system
5. restart the system
6. login as your normal user account
7. Use the now cloned Git repo to setup the other files for the account usng the `setup-home` script. 

The actual commands to obtain and run the the initial script on the freshly installed FreeBSD 10.3 system would be:

```
curl -sL https://goo.gl/sw6oMt -o Install-FreeBSD-10.3
su
sh ./Install-FreeBSD-10.3
shutdown -r now
```

**Note:** the shorten URL of `https://goo.gl/sw6oMt` is used to reduce the typing needed for the actual URL which is:  `https://raw.githubusercontent.com/wiremoons/GenIsys-FreeBSD/master/Install-FreeBSD-10.3`

## Todo

The scripts contain various reminders in the comments (often labled with *TODO:* on what extra features I want to add to the script enventualy.


## License

Any scripts I have authored that are contained on this repo are licensed the **MIT License**.

[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/hyperium/hyper/master/LICENSE)
