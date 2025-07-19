# Login Screen Config

## Raspberry Pi OS

By default, the Raspberry Pi OS greeter (ie. the login screen) restricts you to a single desktop environment.

We don't want to use the default desktop environment. We want to use Plasma Bigscreen.

So we need to switch the default greeter with a different one.

### Automatic

Open a terminal and run:

`sudo sed -i.bak 's/greeter-session=pi-greeter-labwc/greeter-session=lightdm-gtk-greeter/g' /etc/lightdm/lightdm.conf`

This will update your lightdm.conf file and replace the custom Raspberry Pi greeter with the default LightDM one.

It will also create a backup lightdm.conf.bak file.

### Manually

Open a terminal window and run either

`sudo mousepad /etc/lightdm/lightdm.conf`

to edit the file in a graphical text editor, or

`sudo editor /etc/lightdm/lightdm.conf`

to edit the file in a command line text editor.

In either case, search for the line

`greeter-session=pi-greeter-labwc`

and change it to

`greeter-session=lightdm-gtk-greeter`

Do NOT restart LightDM or reboot. That will come later.

## Other Operating Systems

The above step is only necessary because the default greeter for Raspberry Pi OS doesn't let you switch between different desktop environments.

If your OS doesn't restrict you in this way by default (most don't), then you can safely skip this step.

## Next Step

Continue to configuring [Desktop Apps](Desktop.md)