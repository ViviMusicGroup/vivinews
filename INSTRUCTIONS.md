# 📢 ViviNews Announcement Guide: How to Add & Update Announcements

This guide explains step-by-step how to manage announcements, add images and videos, and choose card styles.

---

## 🚀 Quick Step-by-Step: Managing Announcements

The entire announcement lives in `News/1.md`:

```markdown
---
id: 1
title: New Sound Equalizer & Performance Boost
tag: Update
date: Nov 25, 2026
timestamp: 2026-11-25T10:00:00Z
image: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/image/bannerofficial.png
video: null
actionLabel: View on GitHub
actionUrl: https://github.com/ViviMusicGroup/vivi-music
dismissible: true
---

# 🎚️ New Equalizer & Audio Improvements

We are excited to bring advanced audio equalization to ViviMusic!

### What's New in this Build:
- **10-Band Graphic Equalizer**: Custom presets for Bass Boost, Vocal, and Classical.
- **Lower Battery Usage**: Optimized playback pipeline saves up to 15% battery.
- **Bug Fixes**: Resolved intermittent playback stops during background caching.

### Useful Links
- Join our discussion on [Telegram](https://t.me/vivimusic)
- Check out the source code on [GitHub](https://github.com/ViviMusicGroup/vivi-music)

Enjoy listening!
```

### Publishing Updates
Whenever you have a new update, edit `News/1.md`, change the `id` (e.g. `id: 2`), and commit. The app will immediately display the new announcement!

---

## 🎨 Choosing Card Designs: Large vs Small

| Design Style | When to Use | How to Configure in Frontmatter |
| :--- | :--- | :--- |
| **Large Expressive Card** | When you have a banner image or update video | Provide `image:` URL or `video:` URL |
| **Small Compact Card** | When you want a quick text-only notice, maintenance alert, or message | Set `image: null` and `video: null` |

---

## 🖼️ How to Add Images & Videos

### Adding an Image:
1. Place your image in the `image/` folder (e.g. `image/v2_release.png`).
2. In `News/1.md`, set:
   ```yaml
   image: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/image/v2_release.png
   ```

### Adding a Video:
1. Place your video in the `video/` folder (e.g. `video/preview_demo.mp4`).
2. In `News/1.md`, set:
   ```yaml
   video: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/video/preview_demo.mp4
   ```

---

## ⏸️ How to Hide Announcements When There Is No News

If you don't want any card showing on the Home screen:
```markdown
---
active: false
---
```
ViviMusic will automatically hide the announcement section until you set `active: true`.
