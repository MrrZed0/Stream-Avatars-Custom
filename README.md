# Streamer.bot Viewer Avatar Overlay

A **browser-based avatar overlay for Twitch streams** that works with **Streamer.bot WebSocket events**.

Viewers appear on screen as animated avatars that walk across the bottom of the stream, display chat bubbles, and react to commands. Avatars are synchronized using the **Twitch Present Viewers list** so viewers appear when they join and disappear with a **poof effect** when they leave.

This project is inspired by **Evotars** but designed specifically for **Streamer.bot**.

---

# Features

## Viewer Avatars

- Avatars appear when a viewer joins the **Present Viewers list**
- Each avatar has:
  - Twitch profile image as body
  - random color
  - random character skin
- Avatars **walk left and right across the screen**

## Chat Integration

- Chat messages appear as **speech bubbles above avatars**
- **Twitch emotes render as actual images**

Supported commands:

| Command | Description |
|-------|-------------|
| `!grow` | Avatar grows until the user speaks again |
| `!jump` | Avatar jumps |
| `!skin <name>` | Change avatar skin |
| `!color <name>` | Change avatar color |

---

## Viewer Tracking

Uses **Streamer.bot Present Viewers** as the source of truth.

Behavior:

- viewer appears → avatar spawns
- viewer disappears → avatar removed with **poof effect**

To prevent Twitch viewer list flicker, avatars are only removed after being missing for multiple updates.

---

## Raid Support

When a raid occurs:

- Raiders fall from the top of the screen
- Then begin walking like normal avatars

---

## Anti-Duplicate System

Usernames are normalized to lowercase to prevent duplicates when:

- Twitch display names change
- viewers refresh Twitch
- Streamer.bot sends duplicate chat events

---

# Requirements

- **Streamer.bot**
- **OBS Studio (Browser Source)** or overlay software
- **Streamer.bot WebSocket Server enabled**

Default WebSocket server:
