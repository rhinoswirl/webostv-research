# GetMeIn (< webOS 3.3.4)

GetMeIn is an old webOS exploit that targets devices with webOS versions up to 3.3.4.

The exploit consisted on sending a `root` binary to the TV using the jailed ssh session, giving it proper permissions and running it:

```
chmod +x root
./root
```

For webOS verions 3.5+ please see [RootMyTV](rootmytv.md).