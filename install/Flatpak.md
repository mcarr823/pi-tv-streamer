# Flatpak/Flathub

Before you proceed any further, I'm going to suggest that you install Flatpak and add Flathub as a repository on your system.

Flatpaks provide a consistent way to install apps on desktop Linux operating systems.

Later sections of this guide will assume that you have flatpak/flathub installed and setup.

I recommend doing this straight away after booting your newly installed OS, before you do anything else, because you will need to reboot afterwards in order to actually run (and configure) the apps installed this way.

* Note that you can follow most of the instructions in this repository _without_ using flatpak. However, you will need to figure out the alternative directories to use and not just copy and paste the commands given by this repository as-is.

## Install Flathub and Flatpak on Raspberry Pi OS

Flathub [provides instructions](https://flathub.org/setup/Raspberry%20Pi%20OS) for installing Flatpak and adding Flathub as a repository.

In short, you should open a terminal and run

`sudo apt install -y flatpak`

to install flatpak, then

`flatpak --user remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo`

to add Flathub to your list of repositories.

* You can install flatpak apps right away, but you won't be able to run them until after you've rebooted.

## Install Flathub and Flatpak on other operating systems

The instructions should be pretty much the same on most operating systems.

The main difference will be the package manager (apt vs dnf vs pacman and so on).

Also, some distributions already have flatpak (and even flathub) installed on them by default.

If you aren't sure where your chosen operating system sits, check the [list of distributions](https://flathub.org/setup) noted by flathub for more information.

## Reboot

If flatpak _wasn't_ installed prior to this steom then you will need to reboot before proceeding.

This is necessary so that your system can recognize and run flatpaks properly.

Reboot now, then proceed to the next step.

## Next Step

Continue to [Desktop Environment](DE.md)