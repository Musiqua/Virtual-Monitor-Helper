# Not completely tested! Use at your own peril.

This fork modifies Virtual Monitor Helper to use the [itsmikethetech/Virtual-Display-Driver](https://github.com/itsmikethetech/Virtual-Display-Driver) fork of IddSampleDriver. No binaries are provided.

# Virtual Monitor Helper for MTT
A little system tray utility for those who wish to use Sunshine and Moonlight in conjunction with the MTT fork of IddSampleDriver as an external display.  It ensures that Sunshine's configuration file is kept up to date with IddSampleDriver's display name and gracefully handles Windows display configuration changes.

When launched, it will determine the display ID currently associated with IddSampleDriver, write that value to the output_device field of Sunshine's configuration file
and then restart the Sunshine service.  It will then listen continuously for changes to Windows display configuration (resolution changes, connections, disconnects and so on).  
When such a change is detected, it will check to see whether IddSampleDriver's display ID has changed.  If the display ID has changed, then it will update Sunshine's configuration file and restart the
Sunshine service.

If the IddSampleDriver device crashes, is disabled or otherwise lost, the helper will wait until it returns and then perform its tasks.
