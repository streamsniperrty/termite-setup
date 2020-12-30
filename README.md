# termite-setup
My installation and configuration guide to Termite.

## INSTALLING TERMITE (AND VTE-NG, IF REQUIRED)

In order to install the terminal, you may need to install additional software, depending on your distribution. Let's start off with the easy one first, Arch Linux.

### Arch Linux

For Arch Linux based systems, which also includes Manjaro, you need to run one command, saving you all the hassle.

`sudo pacman -S termite`

### Debian

For Debian based systems, which also include Ubuntu and Linux Mint, you won't have the Termite package available in the default repos. Therefore, you will need to compile it from source.

#### Dependencies

Copy and paste this line into a terminal to install the required dependencies.

`sudo apt install gtk-doc-tools intltool libpcre2-dev libghc-gnutls-dev libwebkit2gtk-4.0-dev libgtk-3-dev`

#### vte-ng Installation

Copy the set of commands in order to install the vte-ng project, which is required with Termite.

`git clone https://github.com/thestinger/vte-ng.git`

`cd vte-ng/`

`./autogen.sh --disable-introspection --disable-vala`

`make`

`sudo make install`

#### Termite Installation

Copy the set of commands in order to install the Termite terminal emulator.

`git clone --recursive https://github.com/thestinger/termite.git`

`cd termite && make`

`sudo make install`

#### Special Variable

This variable might be needed if Termite "doesn't act properly". To fix this, you'll need to add a variable to `.bashrc`.

`echo "TERM=termite" >> $HOME/.bashrc`

Once the installation is complete, you can begin with the configuration.
