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

### 🎬 How to Play Video Directly on the HomeScreen:
By default, if an image is provided, the card displays the image banner and plays the video when opened. If you want the video to play **directly inside the HomeScreen card box**, you have two easy options:

1. **Explicit Option (Works even if `image` is also provided)**:
   ```yaml
   previewMedia: video
   ```
2. **Simple Option**:
   Provide `video:` and set `image: null`:
   ```yaml
   image: null
   video: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/video/sample_update.mp4
   ```

---

## ⏳ Automatic Expiration (Date & Time)

You can set an announcement to automatically expire and vanish by specifying `expires:`:

```yaml
# Expires at the end of the specified date (23:59:59)
expires: 2026-12-05

# Or specify an exact UTC time
expires: 2026-12-05T18:00:00Z
```

When the expiration date passes, the app will automatically hide the card from all users and new installs—no manual action required!

---

## ⏸️ How to Hide Announcements When There Is No News

If you don't want any card showing on the Home screen:
```markdown
---
active: false
---
```
ViviMusic will automatically hide the announcement section until you set `active: true`.
