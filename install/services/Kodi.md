# Kodi/XBMC

Kodi has a web version, but it is disabled by default.

The web version is only suitable for cases where your videos are on a separate device than the one being used to play them.

eg. If you watch videos on a Raspberry Pi, but store them on a NAS or home server, and both devices run Kodi.

The desktop application is suitable for either case. It doesn't matter if the videos are on your device or if they're hosted elsewhere, it'll work either way.

## Web Version

If you want to use the web version, check [Kodi's official documentation](https://kodi.wiki/view/Web_interface) for instructions.

## Desktop Version

<details>

Assuming you followed the steps earlier in this guide, you should already have Flatpak/Flathub setup on your system.

If so, run:

`flatpak install -y flathub tv.kodi.Kodi`

Or, if your desktop environment supports it, you can simply search for Kodi in your operating system's "app store", such as KDE Discover.

![Screenshot](screenshots/KodiDiscover.png)

* Warning! Some stores will install the Snap or Native version of Kodi instead of the flatpak version. This is fine, but you may need to figure some things out yourself during later steps, since the instructions in this repository were written for the Flatpak version.

</details>

## Post-install

### Media sources

Add any desired media sources or plugins to your Kodi installation and verify that they're accessible.

Some sources may require a username and password, or a URL, which will be easier to enter now with a keyboard.

### SlyGuy repository and addons

I recommend installing the [SlyGuy Kodi repository](SlyGuy.md).

It contains addons for a wide variety of streaming services, and makes for a streaming experience much more similar to an Android TV box in terms of streaming service availability.

## Next Step

Go back to [services list](README.md)