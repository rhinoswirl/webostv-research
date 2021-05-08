# RootMy.TV (WIP)

Authors: retroid

The payload takes advantage of an additional permission that LG official apps have, which allows them to call DownloadManager in a privileged mode where it is allowed to download files to any location of the system.

The dev payload available on xda replaces `start-devmode.sh` which is checked on the TV boot to check if devmode is enabled and start it.

By changing its contents, it is possible to gain full control over the TV as any commands on that sh file are run as the root user.

https://forum.xda-developers.com/t/rootmy-tv-coming-soon-developer-pre-release-available-now.4232223/