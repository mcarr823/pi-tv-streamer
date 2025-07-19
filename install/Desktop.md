# Desktop Apps

Most streaming services don't provide desktop clients for Linux.

If you use self-hosted streaming services, however, then you're in luck. Those generally have a Linux desktop version.

* The desktop applications in this guide (Jellyfin and Kodi) both have web versions as well. So if you'd rather use the web versions, just skip this section.

## Flatpak/Flathub

Before you proceed any further, I'm going to suggest that you install Flatpak and add Flathub as a repository on your system.

Flatpaks provide a consistent way to install apps on desktop Linux operating systems.

Later sections of this guide will assume that you have flatpak/flathub installed and setup.

### Install Flathub and Flatpak on Raspberry Pi OS

Flathub [provides instructions](https://flathub.org/setup/Raspberry%20Pi%20OS) for installing Flatpak and adding Flathub as a repository.

In short, you should open a terminal and run

`sudo apt install -y flatpak`

to install flatpak, then

`flatpak --user remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo`

to add Flathub to your list of repositories.

* You can install flatpak apps right away. But if flatpak wasn't installed on your system until now, you won't be able to run them until after you've rebooted.

### Install Flathub and Flatpak on other operating systems

The instructions should be pretty much the same on most operating systems.

You can probably just use the above instructions as-is.

The main difference with other distributions will be that some already have flatpak (and even flathub) installed on them by default.

If they aren't preinstalled, check the [list of distributions](https://flathub.org/setup) noted by flathub.

## Install some apps

Once you've got flatpak/flathub setup, check the [services list](../services/README.md) for instructions on how to install some common streaming software.

* Again, you can install flatpak apps right away. But if flatpak wasn't installed on your system until now, you won't be able to run them until after you've rebooted.

## Next Step

Continue to [Browser Setup](browser/README.md)