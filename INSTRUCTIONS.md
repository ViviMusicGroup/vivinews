# 📢 ViviNews Announcement Guide: How to Add & Upgrade Announcements

This guide explains step-by-step how to publish new announcements, add images and videos, choose between the Large and Small card styles, and manage releases.

---

## 🚀 Quick Step-by-Step: Publishing a New Announcement

Whenever you have a new statement, feature update, or notice to share:

### Step 1: Create your archive files (Optional but recommended)
If your last announcement was #1, create:
- `News/slim/2.md`
- `News/detail/2.md`

### Step 2: Write your announcement

#### 📄 A. The Home Card Preview (`News/slim/latest.md` & `News/slim/2.md`)
This file controls what appears on the ViviMusic Home screen:

```markdown
---
id: 2
title: New Sound Equalizer & Performance Boost
summary: Experience crystal-clear audio with our brand-new 10-band equalizer and reduced memory footprint.
tag: Update
date: Nov 25, 2026
timestamp: 2026-11-25T10:00:00Z
image: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/image/bannerofficial.png
video: null
actionLabel: View on GitHub
actionUrl: https://github.com/ViviMusicGroup/vivi-music
dismissible: true
---
```

#### 📄 B. The Full Detail Story (`News/detail/latest.md` & `News/detail/2.md`)
This file is displayed inside the Modal BottomSheet when the user clicks the card:

```markdown
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

### Step 3: Copy to `latest.md`
- Copy the content of `News/slim/2.md` into `News/slim/latest.md`.
- Copy the content of `News/detail/2.md` into `News/detail/latest.md`.

### Step 4: Commit and Push
```bash
git add .
git commit -m "feat(news): publish announcement #2"
git push origin main
```
The app will immediately detect `id: 2` on next launch or pull-to-refresh!

---

## 🎨 Choosing Card Designs: Large vs Small

| Design Style | When to Use | How to Configure in `slim/latest.md` |
| :--- | :--- | :--- |
| **Large Expressive Card** | When you have a banner image or update video | Provide `image:` URL or `video:` URL |
| **Small Compact Card** | When you want a quick text-only notice, maintenance alert, or message | Set `image: null` and `video: null` |

### Small Card Example (`slim/latest.md`):
```markdown
---
id: 3
title: Scheduled Server Maintenance Tonight
summary: YouTube Music sync services may experience brief pauses between 02:00 and 03:00 UTC.
tag: Notice
date: Nov 26, 2026
timestamp: 2026-11-26T02:00:00Z
image: null
video: null
actionLabel: Status Page
actionUrl: https://github.com
dismissible: true
---
```

---

## 🖼️ How to Add Images & Videos

### Adding an Image:
1. Place your image in the `image/` folder (e.g. `image/v2_release.png`).
2. Commit and push it.
3. In `News/slim/latest.md`, set:
   ```yaml
   image: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/image/v2_release.png
   ```

### Adding a Video:
1. Place your video in the `video/` folder (e.g. `video/preview_demo.mp4`).
2. Commit and push it.
3. In `News/slim/latest.md`, set:
   ```yaml
   video: https://raw.githubusercontent.com/ViviMusicGroup/vivinews/main/video/preview_demo.mp4
   ```
*(Note: Videos play seamlessly inside the Modal BottomSheet with auto-loop and mute controls!)*

---

## 🔗 Supported Formatting & Hyperlinks

In `News/detail/latest.md`, you can use full standard Markdown:
- **Headers**: `# Title`, `## Subtitle`, `### Section`
- **Bold / Italic**: `**bold text**`, `*italic text*`
- **Bullet Lists**: `- Item 1`, `- Item 2`
- **Clickable Hyperlinks**: `[Click here to visit GitHub](https://github.com)`
  *(When clicked by users in ViviMusic, links immediately open in their browser or custom tab)*
- **Inline Images**: `![Screenshot](https://raw.githubusercontent.com/.../screenshot.png)`

---

## ⏸️ How to Hide Announcements When There Is No News

If you don't want any card showing on the Home screen:
In `News/slim/latest.md`, set:
```markdown
---
active: false
---
```
ViviMusic will automatically hide the announcement section until you set `active: true` or post a new announcement.

---

## 🏷️ Frontmatter Reference Table

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | String / Number | Unique identifier (e.g. `1`, `2`, `vivi_v2`). Changing this alerts the app to show the new announcement even to users who dismissed earlier ones. |
| `title` | String | Card headline (keep under 60 characters for best display). |
| `summary` | String | 1–3 sentence preview shown on the Home screen card. |
| `tag` | String | Category pill (e.g., `Update`, `News`, `Notice`, `Poll`). |
| `date` | String | Display date (e.g. `Nov 25, 2026`). |
| `timestamp` | ISO String | Optional ISO timestamp (e.g. `2026-11-25T10:00:00Z`). |
| `image` | String (URL) | Direct URL to a PNG/JPG/WebP banner image. |
| `video` | String (URL) | Direct URL to an MP4 video clip. |
| `actionLabel` | String | Text for the bottom sheet primary button (e.g. `Download Update`, `View on GitHub`). |
| `actionUrl` | String (URL) | URL opened when clicking the primary button. |
| `dismissible` | Boolean | `true` if users can close the card with the 'X' button; `false` for mandatory notices. |
