# TV Monitor

See how fast your TV's internet really is, and whether it's fast enough for 4K, while you watch.

A network and system monitor for **Fire TV, Google TV and Android TV**. **This is a test version.** Thanks for trying it!

## Download
**[Download TVMonitor.apk](https://github.com/FirstMistborn/tv-monitor-releases/releases/latest/download/TVMonitor.apk)** (always the newest version)

On a Fire TV or Google TV, use the **Downloader** app and enter this address:

```
https://github.com/FirstMistborn/tv-monitor-releases/releases/latest/download/TVMonitor.apk
```

## What it does
- **Live speed overlay** that floats over any app (Stremio, YouTube, Plex…). It's coloured green for **4K**, amber for **HD** and red for **SLOW**.
- **Speed test** and **lag test** (ping, jitter, packet loss), with an easy verdict
- Graphs of your speed over the last 2 minutes, 15 minutes, hour and day
- **Data used by each app**, and a log of when the internet dropped
- **System info**: memory, storage, heat, CPU speed, HDR and audio details
- **View on your phone**: watch the live speed and run tests from your phone's browser. Scan a QR code once; there's nothing to install on the phone.
- Lots of overlay choices: position, size, style, colours, or "only show when there's a problem"

## Works on
| Device | Status |
| --- | --- |
| Fire TV Stick 4K Max (Fire OS 8) | Tested |
| TCL Google TV (Android 14) | Tested |
| Other Fire TV / Google TV / Android TV on Android 8 or newer | Should work: **please tell me!** |
| Fire Sticks on Fire OS 5 or 6, Samsung, LG, Roku, Apple TV | Won't work |

## Install
1. Allow apps from unknown sources:
   - **Fire TV:** Settings → My Fire TV → Developer options → Install unknown apps → turn on **Downloader**. If you don't see Developer options: Settings → My Fire TV → About, press OK on the device name 7 times.
   - **Google TV / Android TV:** Settings → Apps → Security & restrictions → Unknown sources → turn on the app you'll download with.
2. Open **Downloader**, enter the address above and install.
3. Open **TV Monitor**. On Fire TV it's under **Apps** (hold Home → Apps).

## Overlay and "data by app" permissions
The overlay and the "data by app" screen each need a permission that many TVs hide. Everything else works without them.

**Google TV / Android TV: no PC needed**
1. Turn on debugging: Settings → System → About, press OK on the build number 7 times. Then Settings → System → Developer options → **USB debugging** on (and **Network debugging**, if it's listed).
2. In TV Monitor go to **Settings → Overlay → Permissions → Allow on this TV**.
3. The TV asks "Allow USB debugging?": move to **Allow** and press OK.
4. Done. You can switch debugging off again.

**Fire TV: needs a PC or Android phone once** (Amazon blocks apps from doing it themselves)
1. Settings → My Fire TV → Developer options → **ADB debugging** on.
2. From a PC with [ADB](https://developer.android.com/tools/releases/platform-tools), or an Android phone with an ADB app, run:
```
adb connect <your-tv-ip>:5555
adb shell appops set com.local.netmonitor SYSTEM_ALERT_WINDOW allow
adb shell appops set com.local.netmonitor GET_USAGE_STATS allow
```
Your TV's IP is under Settings → My Fire TV → About → Network.

3. Switch **ADB debugging** off again. While it's on, other devices on your Wi-Fi can ask to control the TV.

## View on your phone
1. In TV Monitor go to **Settings → Phone**, then set **Phone view** to **On**.
2. On a phone on the **same Wi-Fi**, scan the QR code with the camera and open the link.
3. The phone stays paired. Add the page to your home screen to open it quickly.

It only works on your home Wi-Fi. Only phones that scanned the code (or typed the code) can see anything.

## Privacy
- No accounts, no ads, no tracking. Nothing is sent anywhere except the tests you run: the speed test and lag test connect to Cloudflare, and the lag test also checks your router.
- Everything stays on your TV.

## Feedback
Please [open an issue](https://github.com/FirstMistborn/tv-monitor-releases/issues) or reply on Reddit with:
- Your TV / streaming stick model
- What worked, what didn't, and anything confusing
- Screenshots help a lot (crop out anything personal)

## Updating
Download and install the new version the same way. Your settings are kept.
