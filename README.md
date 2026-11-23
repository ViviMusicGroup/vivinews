# ViviNews Repository

This repository hosts official news, update announcements, images, and videos displayed on the ViviMusic Home screen.

---

## 📁 Repository Structure

```
vivinews/
├── News/
│   └── 1.md                  # Active announcement (frontmatter metadata + markdown body)
│
├── image/
│   └── bannerofficial.png        # Images for announcements
├── video/
│   └── sample_update.mp4         # Videos / clips for announcements
└── README.md
```

---

## 📝 How to Publish or Edit an Announcement

The announcement in `News/1.md` is a single file containing YAML frontmatter (for the card on the Home screen) and full Markdown content (for the detail bottom sheet):

```markdown
---
id: 1
title: Welcome to the New ViviMusic Update!
tag: Update
date: Nov 23, 2026
image: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/image/bannerofficial.png
video: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/video/sample_update.mp4
actionLabel: Join Telegram
actionUrl: https://t.me/vivimusic
secondaryActionLabel: View on GitHub
secondaryActionUrl: https://github.com/ViviMusicGroup/vivi-music
dismissible: true
---

# Welcome to ViviMusic!

Here is our full announcement with **bold text**, bullet points:
- Feature 1: Smooth playback & equalizer
- Feature 2: Rich announcements

Visit [our GitHub](https://github.com/ViviMusicGroup/vivi-music) for more!
```

### 🔘 Dynamic Action Buttons (Flat Keys)
You can configure 1 or 2 dynamic buttons in the bottom sheet using simple flat keys:
* **Single Button**:
  ```yaml
  actionLabel: Join Telegram
  actionUrl: https://t.me/vivimusic
  ```
* **Dual Buttons**:
  ```yaml
  actionLabel: Join Telegram
  actionUrl: https://t.me/vivimusic
  secondaryActionLabel: View on GitHub
  secondaryActionUrl: https://github.com/ViviMusicGroup/vivi-music
  ```

---

### ⏳ Automatic Expiry (Date & Time)
You can optionally add `expires:` so the announcement automatically vanishes when the date passes:
```yaml
expires: 2026-12-05          # Expires at the end of the day
# or
expires: 2026-12-05T18:00:00Z # Expires at exact UTC timestamp
```

---

## ⚠️ Important Note on Repository Visibility
For the ViviMusic Android app to fetch announcements, images, and videos without authentication errors, this repository must be set to **Public** on GitHub.
