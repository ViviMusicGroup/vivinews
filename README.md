# ViviNews Repository

This repository hosts official news, update announcements, images, and videos displayed on the ViviMusic Home screen.

---

## 📁 Repository Structure

```
vivinews/
├── News/
│   └── announcements.json    # The live JSON fetched by the ViviMusic app
├── image/
│   └── bannerofficial.png   # Images for announcements
├── video/
│   └── sample_update.mp4    # Videos / clips for announcements
└── README.md
```

---

## 📝 How to Publish an Announcement

Edit `News/announcements.json` on the `main` branch.

### 1. Large Card (With Image / Video)
When `"imageUrl"` or `"videoUrl"` is provided, ViviMusic displays an expressive large card with a top media banner on the Home screen:

```json
{
  "id": "vivi_news_2026_01",
  "title": "Welcome to the New ViviMusic Update!",
  "summary": "Check out the latest features, improved audio playback, video previews, and UI enhancements.",
  "content": "### What's New in ViviMusic\n\n- Adaptive Home Cards\n- Video Previews\n- Clickable [GitHub Link](https://github.com/ViviMusicGroup/vivi-music)",
  "imageUrl": "https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/image/bannerofficial.png",
  "videoUrl": "https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/video/sample_update.mp4",
  "tag": "Update",
  "date": "Nov 23, 2026",
  "actionLabel": "View on GitHub",
  "actionUrl": "https://github.com/ViviMusicGroup/vivi-music",
  "isDismissible": true
}
```

### 2. Small Card (Text Only)
Set `"imageUrl": null` and `"videoUrl": null`. ViviMusic will automatically render a compact, elegant small card without media headers:

```json
{
  "id": "vivi_news_2026_02",
  "title": "Scheduled Server Maintenance",
  "summary": "Our backend sync servers will undergo brief maintenance tonight from 02:00 to 03:00 UTC.",
  "content": "Backend services may experience temporary interruptions during this window.",
  "imageUrl": null,
  "videoUrl": null,
  "tag": "Maintenance",
  "date": "Nov 24, 2026",
  "actionLabel": null,
  "actionUrl": null,
  "isDismissible": true
}
```

---

## ⚠️ Important Note on Repository Visibility
For the ViviMusic Android app to fetch `announcements.json`, images, and videos without requiring GitHub personal access tokens or user authentication, this repository should be set to **Public** on GitHub.
