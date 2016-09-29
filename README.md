# Arc-Colora Theme

##The goal is to make scripts that make it easy to change the colours of the Arc-Theme
Source can be found at https://github.com/horst3180/

###A youtube tutorial can be found here :

###http://erikdubois.be/change-colour-arc-theme-horst3180/


[Sardi icons](https://sourceforge.net/projects/sardi/files/) uses also the term COLORA to indicate that the icons can be ANY colour. Hope this will be more transparent to the end-user.

##Arc COLORA is capable to have ANY colour YOU like.

###Create your own colour accent theme with these scripts.

Arc is a flat theme with transparent elements for GTK 3, GTK 2 and Gnome-Shell which supports GTK 3 and GTK 2 based desktop environments like Gnome, Unity, Budgie, Pantheon, XFCE, Mate, etc.


Each time I run these scripts, I renamed the result from 

    Arc to Arc-Sun
    Arc-Dark to Arc-Dark-Sun
    Arc-Darker to Arc-Darker-Sun

Sun is just the name of the colour. You can choose any name.

Other names and themes that I created are in the themes <b>folder</b>. They are always 'old'.

If you run the scripts on the latest version of the github of Horst <b>then</b> you will have the most recent version with the latest bug fixes.


# Just want to download the themes not build them.

Building takes approx. 20 minutes.

Check the folder <b>themes</b> : 

Here is what you can download: 

All of them have three variants. Not only the Dark version.

##Arc-Sun

A screenshot of the Arc-Sun theme

![Screenshots](http://i.imgur.com/ck1grBn.jpg)

##Arc-Dark-Sun

A screenshot of the Arc-Darker-Sun theme]

![Screenshots](http://i.imgur.com/QnFBXN7.jpg)

###Arc-Darker-Sun

A screenshot of the Arc-Dark-Sun theme

![Screenshots](http://i.imgur.com/lVF7Wj0.jpg)

##A screenshot of the Arc-Dark-Fab theme

![Screenshots](http://i.imgur.com/PbRDWxU.jpg)

##A screenshot of the Arc-Dark-Luv theme

![Screenshots](http://i.imgur.com/c3OTQLZ.jpg)

##A screenshot of the Arc-Dark-Tomato theme

![Screenshots](http://i.imgur.com/jhuHWu8.png)

##A screenshot of the Arc-Dark-Red theme

![Screenshots](http://i.imgur.com/6FcWAzP.jpg)

##A screenshot of the Arc-Dark-Polo theme

![Screenshots](http://i.imgur.com/PBHyYrC.jpg)

##A screenshot of the Arc-Dark-Numix theme

![Screenshots](http://i.imgur.com/vuZ9N2j.jpg)

##A screenshot of the Arc-Dark-Evopop theme

![Screenshots](http://i.imgur.com/0t8HtAP.jpg)

##A screenshot of the Arc-Dark-Paper theme

![Screenshots](http://i.imgur.com/uB4WWNW.jpg)

### Installation

**Important:** The script of Horst3180 is build this way that the output will be to /usr/share/themes and that the directories will be called Arc, Arc-Dark and Arc-Darker. If you have already Arc installed. **It will be overwritten.**

**But we have a script to reinstall the original arc theme at the end.**


To build the arc theme you'll need following applications.

<b>We will install them via script 3.</b>

    * `optipng`
    * `inkscape`
    * `autoconf`
    * `automake`
    * `pkg-config` or `pkgconfig` if you use Fedora
    * `libgtk-3-dev` for Debian based distros or `gtk3-devel` for RPM based distros
    * `git` if you want to clone the source directory



#Install the theme with the following scripts

**0. Get the source**

First install git 

	sudo apt-get install git

Get the latest version from Horst - Arc Theme, clone the repository with

    git clone https://github.com/horst3180/arc-theme

Get the latest version from Arc Colora, clone the repository with

    git clone https://github.com/erikdubois/arc-theme-colora

Copy/paste all scripts inside the directory 

    arc-theme-colora

to 

    arc-theme

Let us run the scripts.

**1. Change the colour**

Use the script to change the colour. Find yourself a nice colour on gpick or online.
It should be a hexadecimal notation WITHOUT the #. Read the script for more info.

	1-change-colors.sh

**2. Delete old assets or png's**

Old png's will have to be deleted. They are still the original blue ones. Read the script for more info.

	2-delete-assets.sh


**3. Make new assets or png's**

This is the most important part. New png's will be created with your colour.

	3-make-assets.sh


**4. Build and install the theme**

    4-final-installation.sh

Other options to pass to autogen.sh are

    --disable-transparency     disable transparency in the GTK3 theme
    --disable-light            disable Arc Light support
    --disable-darker           disable Arc Darker support
    --disable-dark             disable Arc Dark support
    --disable-cinnamon         disable Cinnamon support
    --disable-gnome-shell      disable GNOME Shell support
    --disable-gtk2             disable GTK2 support
    --disable-gtk3             disable GTK3 support
    --disable-metacity         disable Metacity support
    --disable-unity            disable Unity support
    --disable-xfwm             disable XFWM support

    --with-gnome=<version>     build the theme for a specific Gnome version (3.14, 3.16, 3.18, 3.20)
                               Note: Normally the correct version is detected automatically and this
                               option should not be needed.


**5. Copy and rename the theme**

If all went well you will find the result in this directory

    /usr/share/themes !!

It has now the standard name Arc, Arc-Dark and Arc-Darker.


We will run the last script nr 5

	- to rename the folders 
	- to move the folders to ~/.themes
	- to change the content of the three index.themes

Follow the instructions in the script. It will ask for the name to add behind these standard names.

	Arc-Sun for example


After the installation is complete you can activate the theme with `gnome-tweak-tool` or a similar program by selecting `Mint-Y-Sun`, `Mint-Y-Darker-Sun` or `Mint-Y-Dark-Sun` as Window/GTK+ theme. If you named the theme "Sun". That is just an example.

**6. Erase the theme in /usr/share/themes**

<b>Your personal theme is in ~/.themes with the changed name and changed index.themes IF you ran previous script.</b>

You can erase the ones in /usr/share/themes. 

If you want to erase the original files in the folder

	/usr/share/themes

Run this script

	6-clean-up-usr-share-themes.sh



**7. Reinstall the latest version of the original Arc theme**

The way the script of horst is working, it will make (and overwrite) folders Arc, Arc-Dark and Arc-Darker in the /usr/share/themes. So when we run our script to change the colours, the output of this personal creation will be /usr/share/themes.

If you want the original Arc theme back. Just run this script

    7-install-original-arc-theme-again.sh


# Select the new theme


After the installation is complete you can activate the theme with your theme manager by selecting `Arc-Sun`, `Arc-Darker-Sun` or `Arc-Dark-Sun` as Window/GTK+ theme.



# Uninstall the theme manually

If you renamed the theme to Arc-Sun for example

    sudo rm -rf /usr/share/themes/{Arc-Sun,Arc-Darker-Sun,Arc-Dark-Sun}
    sudo rm -rf /usr/local/share/themes/{Arc-Sun,Arc-Darker-Sun,Arc-Dark-Sun}
    rm -rf ~/.local/share/themes/{Arc-Sun,Arc-Darker-Sun,Arc-Dark-Sun}
    rm -rf ~/.themes/{Arc-Sun,Arc-Darker-Sun,Arc-Dark-Sun}


Report any issues on google+ or on this github.


Enjoy.
