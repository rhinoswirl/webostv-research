# Custom Magic Remote cursors

Cursors are rendered by surface-manager-starfish (surface-manager upstart service) and are loaded from `/usr/share/im`. 

`cursorTypeAszMstN.png` is the default "idle" medium-sized cursor. S/M/L in that filename is cursor size.

`/usr/share/im` needs to be mounted/overlaid early on in the boot process (needs testing), or surface-manager needs to be manually restarted after applying the patch. Stays on between suspends when Quick Start+ is enabled.

Credits: [Informatic](https://gist.github.com/Informatic/1983f2e501444cf1cbd182e50820d6c1)