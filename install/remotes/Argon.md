# Argon

This section covers the Argon IR Remote.

Depending on the store you buy it from, it might be called "Argon IR Remote for Argon ONE V2 and M.2 Cases" or something similar.

## Raspberry Pi OS

### Argon Raspberry Pi case

The Argon IR Remote is intended to be paired with an Argon case.

For example, the "Argon ONE V2 Raspberry Pi 4 Case".

However, it should work with other IR receivers, such as USB dongle IR receivers.

### Argon software

If you haven't already done so, install the Argon software on your Raspberry Pi by opening a terminal and running:

`curl https://download.argon40.com/argon1.sh | bash`

This will install the software needed for controlling the case fans, IR receiver, and any other hardware it contains.

### Configure the remote

With that installed on the Raspberry Pi, open a terminal and run:

`argonone-ir`

Press Y to continue.

Type the number "2", then press enter. Press Y to agree.

Type "1" and press enter.

It will install some packages and set things up for you.

### Make it work with streaming programs

You will want to do one of two opposing things here, depending on how you plan to use the remote.

Argon installs a Kodi keymap by default. This is great _if you only want to use the remote with Kodi_, but it's a problem if you want to use it with other apps.

This is because we need to install a global LIRC config in order to make the remote work with _other_ apps. And we can't have both a global config and a Kodi-specific config, otherwise they'll double up and send the same command to Kodi twice.

So if you are only planning on using a remote with Kodi, you should run:

```bash
mkdir -p ~/.var/app/tv.kodi.Kodi/data/userdata/
cp ~/.kodi/userdata/Lircmap.xml ~/.var/app/tv.kodi.Kodi/data/userdata/
```

That will make the remote will work with the flatpak version of Kodi.

On the other hand, if you want to use the remote with other software, such as Jellyfin, you should follow the [LIRC setup guide](Lirc.md) in this repository (from the "Install XDoTool" step onwards).

## Other operating systems

If you are using a Raspberry Pi, then the above instructions may still work even without Raspberry Pi OS.

If you are using a different device, however, then the Argon remote will likely require [manual setup using LIRC](Lirc.md).

### LIRC config file

The Argon software automatically creates a LIRC config file for Kodi in:

`~/.kodi/userdata/Lircmap.xml`

The contents depend on which case and/or remote you are using.

For example, with a Raspberry Pi 4b and the Argon ONE V2 case, the result was:

```xml
<lircmap>
    <remote device="argon">
        <left>KEY_LEFT</left>
        <right>KEY_RIGHT</right>
        <up>KEY_UP</up>
        <down>KEY_DOWN</down>
        <select>KEY_OK</select>
        <start>KEY_HOME</start>
        <rootmenu>KEY_MENU</rootmenu>
        <back>KEY_BACK</back>
        <volumeplus>KEY_VOLUMEUP</volumeplus>
        <volumeminus>KEY_VOLUMEDOWN</volumeminus>
    </remote>
</lircmap>
```

It also created a LIRC system config file at: `/etc/lirc/lircd.conf.d/argon.lircd.conf`

For example:

```
#
# Based on NEC templates at http://lirc.sourceforge.net/remotes/nec/
# Configured codes based on data gathered
#

begin remote
  name  argon
  bits           32
  flags SPACE_ENC
  eps            20
  aeps          200

  header       8800  4400
  one           550  1650
  zero          550   550
  ptrail        550
  repeat       8800  2200
  gap          38500
  toggle_bit      0

  frequency    38000

      begin codes
          KEY_UP                0x00ff53ac
          KEY_DOWN                0x00ff4bb4
          KEY_LEFT                0x00ff9966
          KEY_RIGHT                0x00ff837c
          KEY_VOLUMEUP                0x00ff01fe
          KEY_VOLUMEDOWN                0x00ff817e
          KEY_OK                0x00ff738c
          KEY_HOME                0x00ffd32c
          KEY_MENUBACK                0x00ffb946
      end codes
end remote
```

You should be able to use those configurations on any Linux operating system, including on non Raspberry Pi devices, without needing the Argon software.

In general this should involve [installing lirc](Lirc.md), then creating the two files above.

* The first file is only needed if you plan on using Kodi exclusively. See the "Make it work with streaming programs" section above.

## Next Step

Back to [Remote Control list](README.md)
