# 📺 DARNELL IPTV - Bay Area Free Channels

**Dedicated Autonomous Resource for Natural Exchange and Lifelong Learning**

A curated collection of free, legal IPTV streams for the San Francisco Bay Area, optimized for Jellyfin on DARNELL (HP EliteDesk 800 G4 running WSL/Ubuntu).

---

## 🌉 What's Included

### Bay Area Local Channels
- **KQED PBS** (Channel 9) - Public Broadcasting
- **KRON 4 News** - Independent local news
- **CBS News Bay Area** (KPIX 5) - CBS local coverage
- **NBC Bay Area** (KNTV 11) - NBC news feed
- **ABC7 San Francisco** (KGO) - ABC Localish content

### National Feeds
- **PBS National** - Public broadcasting nationwide
- **ABC News Live** - 24/7 ABC news stream
- **NBC News Now** - 24/7 NBC news stream
- **CBS News National** - 24/7 CBS news stream

---

## 🚀 Quick Setup

### For Jellyfin (Recommended)
1. Go to **Dashboard → Live TV → Add Tuner**
2. Select **M3U Tuner**
3. Enter this URL:
   https://raw.githubusercontent.com/YOUR-USERNAME/darnell-iptv/main/bay-area.m3u
4. Add EPG (Program Guide):
   https://iptv-org.github.io/epg/guides/us/tvguide.com.epg.xml.gz
5. Save and refresh channels

### For VLC/Kodi/Other Players
Download `bay-area.m3u` and open it directly in your media player.

---

## 🔄 Auto-Update Setup (Linux/WSL)

Keep your playlist fresh automatically:

### 1. Create Update Script
```bash
sudo nano /usr/local/bin/update-iptv.sh
```
Paste:
```bash
#!/bin/bash
curl -s https://raw.githubusercontent.com/YOUR-USERNAME/darnell-iptv/main/bay-area.m3u -o /srv/iptv/bay-area.m3u
```
### 2. Make Executable
```bash
sudo chmod +x /usr/local/bin/update-iptv.sh
```
### 3. Schedule Daily Updates
```bash
crontab -e
```
Add this line:
`0 3 * * * /usr/local/bin.update-iptv.sh`

➕ Adding New Channels
Format
m3u

#EXTINF:-1 tvg-id="CHANNEL_ID" group-title="GROUP_NAME",Channel Display Name
https://stream-url-here.m3u8
Example
m3u

#EXTINF:-1 tvg-id="KTVU.us" group-title="Bay Area",KTVU FOX 2
https://example.com/ktvu/stream.m3u8
Finding Streams
iptv-org GitHub - Largest open-source collection
Free-TV GitHub - Curated free streams
Station websites - Many offer direct HLS streams
Testing Streams
bash

ffprobe -v error https://stream-url.m3u8
or

bash

vlc https://stream-url.m3u8
🛠️ Troubleshooting
Stream Not Playing
Test the URL directly in VLC
Check if the stream requires geo-restriction bypass
Verify the stream is still active (streams change frequently)
Jellyfin Not Updating
bash

# Manual refresh
sudo /usr/local/bin/update-iptv.sh
sudo systemctl restart jellyfin
Cron Not Running (WSL)
bash

# Check status
sudo service cron status

# Start manually
sudo service cron start

# Auto-start on WSL boot
echo "sudo service cron start" >> ~/.bashrc
📋 Channel Status
Channel	Status	Last Verified
KQED PBS	✅ Active	2025-01-05
KRON 4	✅ Active	2025-01-05
CBS Bay Area	✅ Active	2025-01-05
NBC Bay Area	✅ Active	2025-01-05
ABC7 SF	✅ Active	2025-01-05
Update this table when you verify streams are working

🔐 Legal Notice
All streams in this playlist are:

Publicly available and free to access
Provided by official broadcasters or authorized distributors
Legal to view in the United States
This playlist does NOT contain:

Pirated content
Unauthorized restreams
Premium cable channels
🏗️ System Specs
DARNELL Configuration:

Hardware: HP EliteDesk 800 G4
OS: Windows 11 + WSL2 (Ubuntu 22.04)
Media Server: Jellyfin 10.9+
Location: Martinez, CA (Bay Area)
📱 Mobile Access
Edit this playlist from anywhere:

Install GitHub mobile app
Navigate to bay-area.m3u
Tap edit (pencil icon)
Make changes and commit
DARNELL syncs automatically at 3 AM
🤝 Contributing
Found a working Bay Area stream? Submit a pull request!

Guidelines
Must be free and legal
Must be stable (not temporary/event streams)
Must be relevant to Bay Area or national news/PBS
Include tvg-id and proper group title
📞 Support
Issues with this playlist? Open a GitHub issue or check:

Jellyfin Documentation
IPTV-Org Community
📜 License
This playlist is provided as-is for personal use. Stream URLs are property of their respective broadcasters.

Last Updated: January 5, 2025
Maintained by: bruh (Martinez, CA)
Built for: DARNELL - Dedicated Autonomous Resource for Natural Exchange and Lifelong Learning

code


---

## 🎯 **What This README Does**

✅ **Documents everything** - Setup, troubleshooting, adding channels  
✅ **Looks professional** - Clean formatting, emojis, tables  
✅ **Easy to maintain** - Update the status table when you verify streams  
✅ **Mobile-friendly** - Readable on GitHub mobile app  
✅ **Legal clarity** - Makes it clear this is all legitimate content  

---

## 🔄 **Next Steps**

1. **Create the README** in your GitHub repo (copy/paste the markdown above)
2. **Replace `YOUR-USERNAME`** with your actual GitHub username in the URLs
3. **Update the "Last Updated" date** whenever you modify the playlist
4. **Star your own repo** so it's easy to find later

---

Want me to also create a **CHANGELOG.md** file to track when you add/remove channels? Tha
