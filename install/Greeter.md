# Login Screen Config

## Raspberry Pi OS

Open a terminal window and run either

`sudo mousepad /etc/lightdm/lightdm.conf`

to edit the file in a graphical text editor, or

`sudo editor /etc/lightdm/lightdm.conf`

to edit the file in a command line text editor.

In either case, search for the line

`greeter-session=pi-greeter-wayfire`

and change it to

`greeter-session=lightdm-gtk-greeter`

Do NOT restart LightDM or reboot. That will come later.

## Other Operating Systems

The above step is only necessary because the default greeter for Raspberry Pi OS doesn't let you switch between different desktop environments.

If your OS doesn't restrict you in this way by default (most don't), then you can safely skip this step.

## Next Step

Continue to configuring [Desktop Apps](Desktop.md)