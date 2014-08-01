Super Cool Awesome Blog Post Name - Subtitle, lucyw thinks the old name was bad
===============================================================================

At the OSL we have shared workstations, all of which are named after colors. In the NOC, I usually work at emerald.workstation.osuosl.bak (Figure 1).  I use [tmux](https://wiki.archlinux.org/index.php/Tmux) (Figure *) to multiplex so I can have multiple terminals open in a single ssh connection and  connect to my session from anywhere. When splitting the terminal vertically,  the prompt can get so long that it's hard to see the command I'm entering (Figure 2). I'd like my prompt to automatically shorten itself in narrow windows. Fortunately my terminal already knows how much space it has available: $COLUMNS is an environment variable which stores how wide your current terminal is, default unixism is 80.  So in order to save space I'd like to shorten my prompt to only  a directory listing and a colored character replacing the normal $ or >.

Behold! (Figure 3, 4)

Using a case statement and filtering out the name of the workstation from the domain name, I can color code my prompt based on hostname.  This very easily lets me know $HOSTNAME (again this is an environment variable which contains /etc/hostname), and indirectly /usr/bin/whoami since almost every other user will preface their prompt with a $USER.

This was a 10 minute exercise in learning how to write case statements in bash and provide some cute utility to an otherwise stale prompt.  The other thing you might notice is that I directly add the unicode heart into the prompt. This causes difficulty on TTYs and some terminal emulators where it is replaced with a ♦ (which is an ASCII character).  There should be a check to make sure it can be loaded and replacing with something else if it fails. All in all this is just quick hack to make life prettier!

[Source!](https://gist.github.com/dspt/113418b78abebab76d97)

![picture](https://staff.osuosl.org/~pono/bashblog3.png)
