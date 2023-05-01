# rnsavinelli's build of dwm - dynamic window manager

dwm is an extremely fast, small, and dynamic window manager for X.

This fork of [dwm](https://dwm.suckless.org/) has my personal configurations, some patches and modifications.

## Requirements

In order to build dwm you need the Xlib header files.


## Installation

Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

```
git clone https://github.com/rnsavinelli/dwm
cd dwm
make clean install
```

## Running dwm

Add the following line to your .xinitrc to start dwm using startx:

```
exec dwm
```

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

```
DISPLAY=foo.bar:1 exec dwm
```

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

```
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
    sleep 1
done &
exec dwm
```

For a better solution consider using my build of slstatus: <https://github.com/rnsavinelli/slstatus>

Other solutions can be found here: <https://dwm.suckless.org/status_monitor/>

## Configuration

The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
