# 📢 ViviNews Announcement Guide: How to Add & Update Announcements

This guide explains step-by-step how to manage announcements, add images and videos, choose card styles, and customize action buttons.

---

## 🚀 Quick Step-by-Step: Managing Announcements

The entire announcement lives in `News/1.md`:

```markdown
---
id: 1
title: Welcome to the New ViviMusic Update!
tag: Update
date: Nov 25, 2026
image: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/image/bannerofficial.png
video: null
actionLabel: Join Telegram
actionUrl: https://t.me/vivimusic
secondaryActionLabel: View on GitHub
secondaryActionUrl: https://github.com/ViviMusicGroup/vivi-music
dismissible: true
---

# 🎚️ New Announcement Details

Full rich markdown text is displayed here inside the bottom sheet.
```

---

## 🔘 Dynamic Action Buttons

You can show any custom buttons using simplified flat keys in frontmatter:

### Example 1: Telegram Channel Link
```yaml
actionLabel: Join Telegram
actionUrl: https://t.me/vivimusic
```

### Example 2: Dual Action Buttons (Primary + Secondary)
```yaml
actionLabel: Join Telegram
actionUrl: https://t.me/vivimusic
secondaryActionLabel: View on GitHub
secondaryActionUrl: https://github.com/ViviMusicGroup/vivi-music
```

### Example 3: Download APK / Release Link
```yaml
actionLabel: Download Update
actionUrl: https://github.com/ViviMusicGroup/vivi-music/releases/latest
```

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
