# Novaust's build of st

English | [简体中文](README_CN.md)

[st](https://st.suckless.org/) is a simple terminal emulator for X which sucks less.

## Requirements

In order to build st you need the Xlib header files.

So install `libxinerama` and `libx11` before compiling.

## Patches used

- [st-alpha-0.8.2.diff](https://st.suckless.org/patches/alpha/)
- [st-anysize-0.8.1.diff](https://st.suckless.org/patches/anysize/)
- [st-nordtheme-0.8.2.diff](https://st.suckless.org/patches/nordtheme/)
- [st-scrollback-0.8.4.diff](https://st.suckless.org/patches/scrollback/)

## Installation

Edit config.mk to match your local setup 
(st is installed into the /usr/local namespace by default).

Afterwards enter the following command to build and install st (if necessary as root):


    make clean install


## Running st

If you did not install st with make clean install, 
you must compile the st terminfo with the following command:


    tic -sx st.info


See the man page for additional details.

If you use dwm, by default, you can use the hot key you set to run st.

If not, check your config.h and make sure your termcmd variable is like this:


    static const char *termcmd[]  = { "st", NULL  };


And set corresponding hot key in keys variable.
