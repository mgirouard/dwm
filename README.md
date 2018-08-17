# My Fork of DWM

DWM is a simple, minimal tiling window manager for X11. It's made by
[suckless][0] and this repo contains my fork.

I've made the follwing changes from upstream:

- Added my `config.h` (I generally tweak this often and commit changes once I'm
  happy with them).
- Added a bottomstack layout and set it as the default. The tile layout still
  exists, but has been moved to `layouts[0]`.
- Added a fake fullscreen mod to allow clients which would normally try to
  occupy the full screen to be constrained to only the space allocated to them.
  This is useful especially for web browsers.
- Topbar is off by default.
- Force `borderpx` to be `0` when only one client is visible.

Things to do:

Over time I'll be transitioning this to a Wayland composer. I intend to keep
everything the same because I _like_ dwm -- I'm just not sure I want to keep
X11 around just because of it.

`Rule` will be expanded upon so that they can include geometry an positioning
for floating windows.

---

The original README follows

    dwm - dynamic window manager
    ============================
    dwm is an extremely fast, small, and dynamic window manager for X.


    Requirements
    ------------
    In order to build dwm you need the Xlib header files.


    Installation
    ------------
    Edit config.mk to match your local setup (dwm is installed into
    the /usr/local namespace by default).

    Afterwards enter the following command to build and install dwm (if
    necessary as root):

        make clean install


    Running dwm
    -----------
    Add the following line to your .xinitrc to start dwm using startx:

        exec dwm

    In order to connect dwm to a specific display, make sure that
    the DISPLAY environment variable is set correctly, e.g.:

        DISPLAY=foo.bar:1 exec dwm

    (This will start dwm on display :1 of the host foo.bar.)

    In order to display status info in the bar, you can do something
    like this in your .xinitrc:

        while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
        do
            sleep 1
        done &
        exec dwm


    Configuration
    -------------
    The configuration of dwm is done by creating a custom config.h
    and (re)compiling the source code.

[0]: https://dwm.suckless.org/
