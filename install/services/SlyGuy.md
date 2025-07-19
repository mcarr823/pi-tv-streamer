# SlyGuy Kodi Repository

The SlyGuy Kodi repository provides Kodi addons which enable you to use a variety of different streaming services, such as Disney+, HBO Max, Hulu, and many more.

You can setup the repository by finding the addon author's instructions [here](https://www.matthuisman.nz/2020/02/slyguy-kodi-repository.html).

Alternatively, you can follow the instructions below.

## Install repository

Note that the below assumes you've already installed Kodi, and that it is NOT running.

Also note that the paths below are for the Flatpak version of Kodi, since that is the version detailed by this repository. The paths will be different for the Snap or Native versions, if you install one of those instead.

```bash
# Create the addon directory, if it doesn't exist
mkdir -p ~/.var/app/tv.kodi.Kodi/data/addons

# Enter that directory
cd ~/.var/app/tv.kodi.Kodi/data/addons

# Download the slyguy repository
wget https://slyguy.uk/repository.slyguy.zip

# Extract it
unzip repository.slyguy.zip

# Delete the zip file
rm repository.slyguy.zip
```

## Enable repository

Open Kodi, then go to Settings -> Add-ons -> All -> SlyGuy Repository, then click on Enable.

## Install add-ons

Go back to the Kodi home screen and go into the Add-ons menu.

* The add-on list might still be updating, if the repository has only just been enabled.

Go to Install From Repository and select SlyGuy Repository -> Video Add-ons, then install any add-ons you want to use.

## Configure add-ons

Installed add-ons should prompt for any necessary configuration (such as login credentials) when you try to use them.

## More information

If you need further information about the SlyGuy repository, or if you're having issues with any of the add-ons, please refer to the [author's website](https://www.matthuisman.nz/).

## Next Step

Go back to [services list](README.md)