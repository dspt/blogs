Super Cool Awesome Blog Post Name - Subtitle, lucyw thinks the old name was bad
===============================================================================

At the OSL our workstations are shared and name after colors.  emerald.workstation.osuosl.bak is where I usually sit in the NOC (Figure 1).  I use tmux (Figure *) to multiplex so I can connect to my session from anywhere, but when splitting the terminal to get a side by side, very often the prompt can get obscenely long (Figure 2). This calls for shortening the bash prompt in order to maximize utility of $COLUMNS.

Behold! (Figure 3, 4)

Using a case statement and filtering out the color from the hostname I color code my prompt based on hostname.  This very easily lets me know $HOSTNAME, and indirectly /usr/bin/whoami since almost every other user will preface their prompt with a $USER.

This was a 10 minute addition in learning how to write case statements in bash and provide some cute utility to an otherwise stale prompt.  The other thing you might notice that is I directly add the unicode heart into the prompt, this causes difficulty on TTYs and some terminal emulators, so there should be a check to make sure it can be loaded and replacing with something else if it fails.

![picture](https://staff.osuosl.org/~pono/bashblog1.png)
