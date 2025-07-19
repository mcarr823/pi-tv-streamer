# Jellyfin

Jellyfin provides both a web interface and a desktop client.

The web version is suitable for cases where your videos are on a separate device than the one being used to play them.

eg. If you store videos on a NAS or home server which runs Jellyfin, but want to watch them from a Raspberry Pi.

The desktop application is more suitable if you're watching videos from the same device which has them stored.

eg. If you download a video onto your desktop PC and watch it directly from there.

## Web Version

<details>

There is no special setup required for the web version of Jellyfin to work.

It will run by default when installed on a server or NAS.

You should be able to access it on port 8096 of the server's IP address by default.

eg. http://192.168.1.100:8096

Whatever the IP address is, access your self-hosted Jellyfin instance from the Raspberry Pi in your browser, then proceed to the "TV Mode" section further down this page.

* Remember to create a shortcut or PWA! See the Browsers section for instructions on how to do this

</details>

## Desktop Client

<details>

Jellyfin provides [several options](https://jellyfin.org/downloads/clients/) for installing their desktop client.

In this case, the one we want is the "Jellyfin Media Player".

Assuming you followed the steps earlier in this guide, you should already have Flatpak/Flathub setup on your system.

If so, run:

`flatpak install -y flathub com.github.iwalton3.jellyfin-media-player`

Or, if your desktop environment supports it, you can simply search for Jellyfin in your operating system's "app store", such as KDE Discover.

* If you install it this way, make sure you grab "Jellyfin Media Player", not one of the other packages such as "Jellyfin Server".

![Screenshot](screenshots/JellyfinDiscover.png)

* Warning! Some stores will install the Snap or Native version of Jellyfin instead of the flatpak version. This is fine, but you may need to figure some things out yourself during later steps, since the instructions in this repository were written for the Flatpak version.

</details>

## TV Mode

Regardless of how you install Jellyfin, there's one particular step you'll want to take.

That is to put Jellyfin into TV mode, which will make it much easier to use with arrow keys, gamepads, or even a remote control.

<details>

Click on the Menu icon up the top left side of the website/app.

![Screenshot](screenshots/JellyfinSettings01.png)

Click on Settings.

![Screenshot](screenshots/JellyfinSettings02.png)

Click on Display.

![Screenshot](screenshots/JellyfinSettings03.png)

Change the display mode from Auto to TV.

![Screenshot](screenshots/JellyfinSettings04.png)

Scroll down to the bottom of the page and click on Save.

![Screenshot](screenshots/JellyfinSettings05.png)

Afterwards, close and reopen the app/website for the change to take full effect.

</details>

## Next Step

Go back to [services list](README.md)