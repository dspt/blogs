Super Cool Awesome Blog Post Name - Subtitle, lucyw thinks the old name was bad
===============================================================================

At the OSL our workstations are shared and named after colors.  emerald.workstation.osuosl.bak is where I usually sit in the NOC (Figure 1).  I use tmux (Figure *) to multiplex so I can connect to my session from anywhere, but when splitting the terminal to get a side by side, very often the prompt can get obscenely long (Figure 2). This calls for shortening the bash prompt in order to maximize utility of $COLUMNS.$COLUMNS is an environment variable which stores how wide your current terminal is, default unixism is 80.  So in order to save space all I have is a directory listing and a colored character replacing the normal $ or >.

Behold! (Figure 3, 4)

Using a case statement and filtering out the color from the hostname, I color code my prompt based on hostname.  This very easily lets me know $HOSTNAME (again this is an environment variable which contains /etc/hostname), and indirectly /usr/bin/whoami since almost every other user will preface their prompt with a $USER.

This was a 10 minute exercise in learning how to write case statements in bash and provide some cute utility to an otherwise stale prompt.  The other thing you might notice is that I directly add the unicode heart into the prompt. This causes difficulty on TTYs, where it is replaced with a ♦, and some terminal emulators.  There should be a check to make sure it can be loaded and replacing with something else if it fails. All in all this is just quick hack to make life prettier!

```bash
box="${HOSTNAME#*.}"
D=$'\[\e[0m\]'

case "$box" in

aqua)    COLOR=$'\e[1;34m\]'
         ;;
cyan)    COLOR=$'\e[1;36m\]'
         ;;
diamond) COLOR=$'\e[0;37m\]'
         ;;
emerald) COLOR=$'\e[1;32m\]'
         ;;
pink)    COLOR=$'\e[0;35m\]'
         ;;
yellow)  COLOR=$'\e[0;33m\]'
         ;;
esac
```

![picture](https://staff.osuosl.org/~pono/bashblog3.png)
