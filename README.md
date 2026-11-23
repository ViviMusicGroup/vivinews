# ViviNews Repository

This repository hosts official news, update announcements, images, and videos displayed on the ViviMusic Home screen.

---

## 📁 Repository Structure

```
vivinews/
├── News/
│   ├── latest.md             # Active announcement (frontmatter metadata + markdown body)
│   ├── 1.md                  # Announcement #1 (archive)
│   └── 2.md                  # Announcement #2 (archive)
│
├── image/
│   └── bannerofficial.png        # Images for announcements
├── video/
│   └── sample_update.mp4         # Videos / clips for announcements
└── README.md
```

---

## 📝 How to Publish an Announcement

Each announcement in `News/latest.md` is a single unified file containing YAML frontmatter (for the card on the Home screen) and full Markdown content (for the detail bottom sheet):

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

# Welcome to ViviMusic!

Here is our full announcement with **bold text**, bullet points:
- Feature 1: Smooth playback & equalizer
- Feature 2: Rich announcements

Visit [our GitHub](https://github.com/ViviMusicGroup/vivi-music) for more!
```

* **Large Card:** If `image:` or `video:` is provided, the card automatically shows the **Large Expressive Card** with the top media banner (Harmonic Stories style).
* **Small Card:** If `image:` and `video:` are omitted or null, it shows the compact **Small Expressive Card**.
* **Clicking the Card:** Opens the detailed `ModalBottomSheet` displaying full markdown, media, and action buttons.

---

## ⚠️ Important Note on Repository Visibility
For the ViviMusic Android app to fetch announcements, images, and videos without authentication errors, this repository must be set to **Public** on GitHub.
