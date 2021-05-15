# GetMeIn (< webOS 3.3.4)

[GetMeIn](https://forum.xda-developers.com/t/getmein-one-time-rooting-jailbreaking-tool-for-webos-lg-tvs.3887904/) is an old webOS exploit discovered by Maroc-OS that targets devices with webOS versions up to 3.3.4.

The exploit consisted on sending a `root` binary to the TV using the jailed ssh session, giving it proper permissions and running it:

```
chmod +x root
./root
```

For webOS verions 3.5+ please see [RootMyTV](rootmytv.md).

> There are no public exploits for webOS versions >3.3.4 and <3.5.