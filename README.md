# Streamer.bot Viewer Avatar Overlay

A **browser-based avatar overlay for Twitch streams** that works with **Streamer.bot WebSocket events**.

Viewers appear on screen as animated avatars that walk across the bottom of the stream, display chat bubbles, and react to commands. Avatars are synchronized using the **Twitch Present Viewers list** so viewers appear when they join and disappear with a **poof effect** when they leave.

This project is inspired by **Evotars** but designed specifically for **Streamer.bot**.

![Image](https://github.com/MrrZed0/Stream-Avatars-Custom/blob/main/Photo.png?raw=true)
![Image](https://github.com/MrrZed0/Stream-Avatars-Custom/blob/main/333.gif?raw=true)

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
ws://127.0.0.1:8080/


---

# Installation

## 1. Clone the repository
git clone https://github.com/MrrZed0/Stream-Avatars-Custom

### 2. Add the HTML Overlay
OBS → Browser Source
Recommended Resolution: 1920x1080

#### 3. Enable Streamer.bot WebSocket Server
Servers → WebSocket Server


streamer.bot
twitch stream avatars
streamer.bot stream avatars
Stream Avatars
evotars
streamer.bot avatars
