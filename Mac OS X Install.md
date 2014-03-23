# The short, short version.

You need home brew.  Then...

```
brew install libusb
sudo easy_install pyusb
```

Use python to run the script:

```
python ./cgminerLCDStats.py --host MINERIP
```

That is it.

# The slightly longer short version

If you want it to start when you login create a file in ~/Library/LaunchAgents/com.foobar.plist:

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>Label</key>
    <string>com.spencer.minermon</string>
    <key>ProgramArguments</key>
    <array>
        <string>python</string>
	<string>/Users/username/rcs/cgminerLCDStats/cgminerLCDStats.py</string>
        <string>--host</string>
        <string>MINERIP</string>
        <string>--mtgoxDisplayOff</string>
    </array>
    <key>StandardOutPath</key>
    <string>/dev/null</string>
    <key>StandardErrorPath</key>
    <string>/dev/null</string>
    <key>KeepAlive</key>
    <true/>
</dict>
</plist>
```

Start it manually to test:

```
launchctl load ~/Library/LaunchAgents/com.foobar.plist
```

