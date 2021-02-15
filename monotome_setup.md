# Monotome setup

1. Clone repository
2. Create subfolder for wiki content and `git init`
3. Make script for auto pulling and generating index:
```
cd /srv/monotome/antiwiki/
git pull origin master
cd /srv/monotome/
node monotome/bin/generate.js
```
4. Make cron job running the script every minute and logging output

```
* * * * * /srv/monotome/wikipull.sh >> /srv/wikipull.log 2>&1
```

## Optional

5. Make script for starting wiki
```
cd /srv/monotome/
python3 -m http.server 8900
```

6. Make cron job to autostart the script on reboot
```
@reboot /srv/monotome/wikistart.sh >> /srv/wikistart.log 2>&1
```
