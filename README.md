# genius-spicetify
Spotify desktop client app fetches lyrics from Genius

![demo](https://i.imgur.com/nDWy4g9.png)

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
