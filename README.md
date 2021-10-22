# Gruv Theme

Gruv is a flat theme with transparent elements for GTK 3 which supports GTK 3 and Xfce.

This theme is just a hack of Arc Theme. You should really go check that out here: ![](https://github.com/horst3180/arc-theme) he really did
all the hard work. I just ripped it off to make a Gruv colourway of this theme as I kinda like everything Gruv.

## Installation

To build the theme the follwing packages are required 
* `autoconf`
* `automake`
* `pkg-config` or `pkgconfig` for Fedora
* `libgtk-3-dev` for Debian based distros or `gtk3-devel` for RPM based distros
* `git` to clone the source directory

**Note:** For distributions which don't ship separate development packages, just the GTK 3 package is needed instead of the `-dev` packages.

For the theme to function properly, install the following
* GNOME Shell 3.14 - 3.24, GTK 3.14 - 3.22
* The `gnome-themes-standard` package
* The murrine engine. This has different names depending on the distro.
  * `gtk-engine-murrine` (Arch Linux)
  * `gtk2-engines-murrine` (Debian, Ubuntu, elementary OS)
  * `gtk-murrine-engine` (Fedora)
  * `gtk2-engine-murrine` (openSUSE)
  * `gtk-engines-murrine` (Gentoo)

Install the theme with the following commands

#### 1. Get the source

Clone the git repository with

    git clone https://github.com/jnewing/xfce-gruv

#### 2. Build and install the theme

    ./autogen.sh --prefix=/usr
    sudo make install

Other options to pass to autogen.sh are

    --disable-transparency     disable transparency in the GTK3 theme
    --disable-gnome-shell      disable GNOME Shell support
    --disable-gtk3             disable GTK3 support
    --disable-xfwm             disable XFWM support

    --with-gnome=<version>     build the theme for a specific GNOME version (3.14, 3.16, 3.18, 3.20, 3.22)
                               Note 1: Normally the correct version is detected automatically and this
                               option should not be needed.
                               Note 2: For GNOME 3.24, use --with-gnome-version=3.22
                               (this works for now, the build system will be improved in the future)

After the installation is complete the theme can be activated with `gnome-tweak-tool` or a similar program by selecting `Gruv` as Window/GTK+ theme and `Gruv` as GNOME Shell/Cinnamon theme.

If the `--disable-transparency` option was used, the theme will be installed as `Gruv-solid`.

## Uninstall

Run

    sudo make uninstall

from the cloned git repository, or

    sudo rm -rf /usr/share/themes/Gruv
