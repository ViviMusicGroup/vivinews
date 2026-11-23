# ViviNews Repository

This repository hosts official news, update announcements, images, and videos displayed on the ViviMusic Home screen.

---

## 📁 Repository Structure

```
vivinews/
├── News/
│   ├── slim/
│   │   ├── latest.md             # Active card preview fetched for the Home Screen
│   │   ├── 1.md                  # Announcement #1 (archive)
│   │   └── 2.md                  # Announcement #2 (archive)
│   │
│   └── detail/
│       ├── latest.md             # Active detail markdown fetched for the ModalBottomSheet
│       ├── 1.md                  # Full detail #1 (archive)
│       └── 2.md                  # Full detail #2 (archive)
│
├── image/
│   └── bannerofficial.png        # Images for announcements
├── video/
│   └── sample_update.mp4         # Videos / clips for announcements
└── README.md
```

---

## 📝 How to Publish an Announcement

### 1. The Home Card (`News/slim/latest.md`)
Contains the metadata, titles, media links, and short summary displayed on the Home screen card:

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
```

* If `image:` or `video:` is provided, the card automatically shows the **Large Expressive Card** with the top media banner.
* If `image:` and `video:` are omitted or null, it shows the **Small Expressive Card**.

### 2. The Detailed Sheet (`News/detail/latest.md`)
Contains the full rich Markdown text displayed when the user taps the card to open the ModalBottomSheet:

```markdown
# Welcome to ViviMusic!

Here is our full announcement with **bold text**, bullet points:
- Feature 1
- Feature 2

Visit [our GitHub](https://github.com/ViviMusicGroup/vivi-music) for more!
```

---

## ⚠️ Important Note on Repository Visibility
For the ViviMusic Android app to fetch announcements, images, and videos without authentication errors, this repository should be set to **Public** on GitHub.
