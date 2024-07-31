# Firefox

Firefox doesn't support PWAs. However, you can get similar functionality with kiosk mode.

To start with, open Firefox and complete the first-time setup. Just skip through it all.

Then go to the website or streaming service you want to use and login.

After that, you can add the website to your applications list either via the terminal, or via the GUI.

The terminal method should work across most desktop environments, whereas the GUI method will vary depending on the environment.

## Terminal method

<Details>

Open a terminal window and run:

`cd ~/.local/share/applications`

This will take you to the directory where custom application menu entries are stored.

After that, run:

```
NAME=ServiceName
URL=WebsiteUrl
```

to set the environment variables NAME and URL.

NAME should be a plain English name, without any spaces or special characters.

URL should be the website URL copied from your browser's address bar.

For example

```
NAME=Crunchyroll
URL=https://www.crunchyroll.com
```

With those two variables defined, create a desktop file by running:

```
cat <<EOF > $NAME.desktop
[Desktop Entry]
Exec=firefox -kiosk $URL
Name=$NAME
NoDisplay=false
StartupNotify=true
Terminal=false
Type=Application
EOF
```

This should result in a new menu entry being created for the given website, which will open in kiosk mode by default.

Repeat this process for each service you want to use.

</Details>

## GUI method - Raspberry Pi OS

<Details>

Open the pre-installed program called Main Menu Editor.

Then go to Applications -> Internet, and click on New Item.

In the Launcher Properties window, give your website a name and add a command of

`firefox -kiosk URL`

For example:

`firefox -kiosk https://www.crunchyroll.com`

The comment is optional.

You can also add an icon by clicking on the Image button on the left side of the window. You'll need to download a suitable icon from the web.

Click on OK when you're done and that should be it. You'll have a new menu entry for that website which will open in fullscreen (kiosk mode) by default.

* If you already have another browser window open, then the application might not open in fullscreen mode.

</Details>

## GUI method - Other Desktop Environments

There are too many different desktop environments for me to list the steps for each one.

But generally speaking, your desktop environment probably has a Menu Editor program installed by default, similar to the one detailed above.

It is probably called "Menu Editor", or something very similar to that. And the steps are likely very similar to the ones above.

## Exit kiosk mode

Stuck in kiosk mode?

You can make the window no longer fullscreen by pressing Alt + F11.

Or you can just close the window altogether by pressing Alt + F4.

## Next Step

Go back to the [Browser Setup](README.md)