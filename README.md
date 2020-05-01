# genius-spicetify
Spotify desktop client app fetches lyrics from Genius and Musixmatch

![demo](https://i.imgur.com/rbqvJVI.png)

![demo2](https://i.imgur.com/dIkxWQ2.gif)

## How to install
0. Make sure [spicetify-cli]() is installed and run `spicetify apply` normally.
1. Run these commands, one by one:
  
**Linux and MacOS** in Bash:
```bash
cd "$(dirname "$(spicetify -c)")/CustomApps"
git clone https://github.com/khanhas/genius-spicetify
mv "genius-spicetify" genius
```

**Windows** in Powershell:
```powershell
cd "$(spicetify -c | Split-Path)\CustomApps"
git clone https://github.com/khanhas/genius-spicetify
Rename-Item "genius-spicetify" genius
```

3. Finally, run:
```bash
spicetify config custom_apps genius
spicetify apply
```

## How to update
If you already installed before with those steps above, you just need to run these to update:  
**Linux and MacOS** in Bash:
```bash
cd "$(dirname "$(spicetify -c)")/CustomApps/genius"
git pull
```

**Windows** in Powershell:
```powershell
cd "$(spicetify -c | Split-Path)\CustomApps\genius"
git pull
```

## Musicxmatch
I already included a free user token to fetch full and synched lyrics from Musixmatch database. Since Musixmatch has limit rate per token, too many requests with same token will temperory block it from receiving result. Follow these steps to retrieve a personal token:

1. Download and install Musixmatch offical app: https://download-app.musixmatch.com/download  
Windows user: install it via Windows Store.

2. **You don't have to log in!**

3. Now in Musixmatch app, hit `Ctrl + Shift + i` to bring up DevTools.

![mxm1](https://i.imgur.com/jMGMgCc.png)

4. Switch to Network tab. Hit `Ctrl + R`. Filter results with "apic":

![mxm2](https://i.imgur.com/QdwqtQa.png)

5. Click at any result, it will show up request detail panel. Scroll all the way down. Note down `usertoken`

![mxm3](https://i.imgur.com/ZsGwKG3.png)

For example request above, I should note down:
```
200501593b603a3fdc5c9b4a696389f6589dd988e5a1cf02dfdce1
```

6. In `genius` app folder, open file `manifest.json`. In that file, look for `UserToken`, then just fill it in with yours.

8. Restart Spotify and Enjoy!

## Disclaimer
This app assets were taken from `lyrics` app from Spotify team and modified by me. I do not own any of these code and they should not be reused anywhere else.
