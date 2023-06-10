# Port of @bethylamine's Soupcan extension to Safari

## Notes:
Converted using
```shell
git clone https://github.com/bethylamine/soupcan.git
xcrun safari-web-extension-converter --app-name Soupcan --bundle-identifier net.acrossthecloud.Soupcan --project-location ]Soupcan-Safari --swift soupcan/manifest-v3
```

## Known issues:
* The conversion step gave a warning to say the `open_in_tab` option for the options UI is unsupported, but Safari settings > Extensions >  Soupcan > Settings successfully brings up the options page.
* "The service_worker script failed to load due to an error." The `service_worker` script is set to [background.js](https://github.com/bethylamine/soupcan/blob/main/manifest-v3/background.js), but still seems to run.
* Safari settings > Extensions >  Soupcan > PERMISSIONS > needed to be manaully set to twitter.com > Allow, on iOS, but worked with Ask on macOS.
* For development, you will probably want to switch off signing for all four targets (the apps and the corresponding extensions), unless you have a code signing certificate, and at least on macOS [configure Safari to run unsigned extensions](https://developer.apple.com/documentation/safariservices/safari_web_extensions/running_your_safari_web_extension#3744467) (I don't know about iOS)

