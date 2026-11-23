# ViviNews Repository

This repository hosts official news, update announcements, images, and videos displayed on the ViviMusic Home screen.

---

## 📁 Repository Structure

```
vivinews/
├── News/
│   ├── latest.md             # The active announcement fetched by the ViviMusic app
│   ├── 1.md                  # Announcement #1 (archive)
│   └── 2.md                  # Announcement #2 (archive)
├── image/
│   └── bannerofficial.png    # Images for announcements
├── video/
│   └── sample_update.mp4     # Videos / clips for announcements
└── README.md
```

---

## 📝 How to Publish an Announcement

### 1. Large Card (With Image / Video)
When `image:` or `video:` is provided, ViviMusic displays an expressive large card with a top media banner on the Home screen:

```markdown
---
id: 1
title: Welcome to the New ViviMusic Update!
summary: Check out the latest features, improved audio playback, video previews, and UI enhancements.
tag: Update
date: Nov 23, 2026
image: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/image/bannerofficial.png
video: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/video/sample_update.mp4
actionLabel: View on GitHub
actionUrl: https://github.com/ViviMusicGroup/vivi-music
dismissible: true
---

# Details here...
```

### 2. Small Card (Text Only)
Leave `image:` and `video:` empty or omit them. ViviMusic will automatically render a compact, elegant small card without media headers:

```markdown
---
id: 2
title: Scheduled Server Maintenance
summary: Our backend sync servers will undergo brief maintenance tonight from 02:00 to 03:00 UTC.
tag: Maintenance
date: Nov 24, 2026
actionLabel: null
actionUrl: null
dismissible: true
---

# Maintenance Notice
Backend services may experience temporary interruptions during this window.
```

### 3. Workflow for New Announcements
1. Create a copy of your new post as `News/2.md` (for your archive).
2. Copy the content into `News/latest.md`.
3. Commit and push. ViviMusic will immediately fetch `News/latest.md` and show it to users.

---

## ⚠️ Important Note on Repository Visibility
For the ViviMusic Android app to fetch `latest.md`, images, and videos without requiring GitHub personal access tokens or user authentication, this repository should be set to **Public** on GitHub.
