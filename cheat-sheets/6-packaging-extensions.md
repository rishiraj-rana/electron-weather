**Step One**: From your project's root directory:
```sh
mkdir Icons
```
**Step Two**: Find an icon, here: https://useiconic.com/open

**Step Three**: Convert that icon into three filetypes, using this site: https://iconverticons.com/online/
- macOS - .icns
- Windows - .ico
- Linux - .png

**Step Four**: Add each image to the Icons directory.

**Step Five**: Add a build script to your package.json, beginning on line 9, to account for builds with different icons with the scripts below. In the example below, the app name is electron-app, and the icon name is unicorn. You can change that to match your own app and icon name.
```
"build-darwin"  : "electron-packager . electron-app --platform=darwin --icon Icons/unicorn.icns --overwrite",
"build-mas"     : "electron-packager . electron-app --platform=mas --icon Icons/unicorn.icns --overwrite",
"build-linux"   : "electron-packager . electron-app --platform=linux --icon Icons/unicorn.png --overwrite",
"build-win32"   : "electron-packager . electron-app --platform=win32 --icon Icons/unicorn.ico --overwrite",
"build"         : "npm run build-darwin && npm run build-mas && npm run build-linux && npm run build-win32"
```
**Step Six**:
```
npm run build
```

### Troubleshooting Steps
There might be some inconsistencies between electron-packager and the most recent version of node. If the steps above didn’t work for you, try using node 6.11.2 with npm 3.10.10. The following steps should help you do this on macOS.

Note: We’re using nvm here instead of n, or other version manager tools. If you can duplicate successful steps to adjust your node version, please do so (and good luck!).

macOS

**Step One**
```
brew cask install xquartz
```
**Step Two**
```
brew install wine
```
**Step Three**
```
Type brew install nvm
```
**Step Four**
```
nvm install 6.11.2
```
**Step Five**
```
nvm use 6
```
**Step Six**
```
npm run build
```
WARNING – It might take a long time to build the win32 package. Leave this for 5-10 minutes and return.


#### Jump to [Next Exercise](7-refresh.md)
