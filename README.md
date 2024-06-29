# macOS-App-Cleaner

The script was originally written by [sunknudsen](https://github.com/sunknudsen), but his repo is now [archived](https://github.com/sunknudsen/privacy-guides/tree/master/how-to-clean-uninstall-macos-apps-using-appcleaner-open-source-alternative). I didn't want to fork the entire thing, so I only took the app cleaner script to make my own changes.

## Syntax

```console
app-cleaner.sh /path/to/app.app

app-cleaner.sh /path/to/app.app --show
```

## Usage guide

Removing an app:

```console
➜  ~ app-cleaner.sh /Applications/The\ Unarchiver.app
Checking for running processes…
Finding app data…
/Applications/The Unarchiver.app
/Users/kavish/Library/Caches/SentryCrash/The Unarchiver
/Users/kavish/Library/HTTPStorages/com.macpaw.site.theunarchiver
/Users/kavish/Library/HTTPStorages/com.macpaw.site.theunarchiver.binarycookies
/Users/kavish/Library/Preferences/com.macpaw.site.theunarchiver.plist
/var/folders/ft/ypgt74f933qc92fvqqxyhx000000gn/C/com.macpaw.site.theunarchiver
Move app data to trash (yes or n)? yes
Moving app data to trash…
Done
```

Only show app data that will be removed:

```console
➜  ~ app-cleaner.sh /Applications/The\ Unarchiver.app --show
Checking for running processes…
Finding app data…
/Applications/The Unarchiver.app
/Users/kavish/Library/Caches/SentryCrash/The Unarchiver
/Users/kavish/Library/HTTPStorages/com.macpaw.site.theunarchiver
/Users/kavish/Library/HTTPStorages/com.macpaw.site.theunarchiver.binarycookies
/Users/kavish/Library/Preferences/com.macpaw.site.theunarchiver.plist
/var/folders/ft/ypgt74f933qc92fvqqxyhx000000gn/C/com.macpaw.site.theunarchiver
```

> The `--show` flag should always come after the app name and be the last argument.

## Modification

- Added **SentryCrash** location: `$HOME/Library/Caches/SentryCrash`
- Added **Services** location: `$HOME/Library/Services`
- Added **Diagnostic Reports** location: `/Library/Logs/DiagnosticReports`
- Update Prompt to: `Move app data to trash (yes or n)?` 
- Added `--show` flag to only print the app data locations