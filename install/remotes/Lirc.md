# LIRC

LIRC (Linux Infra-Red Control) allows you to send commands to a Linux machine via an infra-red signal.

You can find more information about LIRC [here](https://lirc.org/), including a list of supported remote controls, and their config files.

## Before you begin

Please note that the below will only work for X11 desktop environments, not for Wayland.

Wayland desktop environments in general don't support virtual keyboard input (for security reasons), which means we can't pass arbitrary keystrokes to the desktop via IR.

For Wayland, you currently need to use an application which handles LIRC commands itself (such as Kodi).

## Setup

### Install LIRC

Install the LIRC package.

`sudo apt install -y lirc`

### Setup remote

Find the config for your remote in the [LIRC remotes database](https://lirc-remotes.sourceforge.net/remotes-table.html) (or elsewhere).

Download the file, then copy it to your LIRC config directory.

eg. `cp 2wire.lircd.conf /etc/lirc/lircd.conf.d/`

### Start LIRC

Start the LIRC daemon manually:

`sudo systemctl start lircd`

Or restart it, if lirc was already running prior to the config being added:

`sudo systemctl restart lircd`

Or just wait until you next reboot.

### Install XDoTool

xdotool is used to send commands from LIRC to whichever application (Kodi, Jellyfin, etc.) is currently open.

`sudo apt install -y xdotool`

### Setup IRExec

irexec should already be installed, but it will need one addition.

That is, to run it in the background by default.

You can do this for most desktop environments by opening a terminal and running:

```
cat <<EOF > ~/.config/autostart/irexec.desktop 
[Desktop Entry]
Exec=irexec
Icon=
Name=irexec
Path=
Terminal=False
Type=Application
EOF
```

### Setup LIRC RC

This is the keymap responsible for translating LIRC commands to desktop commands.

eg. To turn the LIRC command KEY_LEFT (the Left button on a remote) to a command a computer understands (eg. a Left arrow key).

Open a terminal and run the below command:

```
cat <<EOF > ~/.config/lircrc
begin
    button = KEY_LEFT
    prog = irexec
    config = xdotool key Left
end

begin
    button = KEY_RIGHT
    prog = irexec
    config = xdotool key Right
end

begin
    button = KEY_UP
    prog = irexec
    config = xdotool key Up
end

begin
    button = KEY_DOWN
    prog = irexec
    config = xdotool key Down
end

begin
    button = KEY_OK
    prog = irexec
    config = xdotool key Return
end

begin
    button = KEY_HOME
    prog = irexec
    config = xdotool getwindowfocus windowkill
end

begin
    button = KEY_BACK
    prog = irexec
    config = xdotool key Escape
end

begin
    button = KEY_VOLUMEUP
    prog = irexec
    config = /usr/bin/pactl -- set-sink-volume 0 +5%  # vol+
end

begin
    button = KEY_VOLUMEDOWN
    prog = irexec
    config = /usr/bin/pactl -- set-sink-volume 0 -5%  # vol-
end
EOF
```

The above maps the following:
- Volume up/down buttons increase/decrease volume by 5%
- Direction buttons on the remote trigger arrow keys
- Middle/OK button triggers the Enter key
- Home button closes the current window/application
- Back button triggers the Esc key

You can change these mappings to your liking.

Just keep in mind that the changes won't take effect until you logout and back in.
