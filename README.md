# NexCord

A mobile Discord client based on Vendroid, rebranded as **NexCord** with exclusive mobile plugins and performance improvements.

## What's different from Vendroid/Vencord?

### Performance
- **No white flash on launch** — dark background loaded before WebView renders
- **Hardware-accelerated WebView** with `LAYER_TYPE_HARDWARE`
- **JS timers paused in background** via `pauseTimers()` — saves battery
- **WebView cache enabled** — faster reloads on repeat visits
- **Async bundle fetch** off the main thread — UI stays responsive
- **Retry dialog** instead of silently crashing on network failure

### Exclusive NexCord Plugins (mobile-only)

| Plugin | What it does |
|---|---|
| **MobileSwipeToReply** | Swipe left on any message to reply (like other mobile chat apps) |
| **MobileStatusBar** | Removes excess top padding, enables smooth scroll, fixes text zoom on rotation |
| **HideBlockedMessages** | Fully removes blocked messages from DOM (vs just collapsing) |
| **MessageTranslate** | Long-press → Translate using LibreTranslate (no API key needed) |
| **ReadAllButton** | Floating "Mark All Read" button appears when you have unread channels |
| **MobileCompactMode** | Toggle tighter message spacing for more content on small screens |
| **CustomFont** | Apply any Google Font to Discord's UI |
| **ImagePreviewExpand** | Tap any image to view fullscreen without leaving the app |
| **MentionSound** | Plays a soft ping when you're @mentioned (Web Audio API, no notification perms) |
| **NexCordSettings** | Settings panel injected into Discord's User Settings |

### Native Android Bridge (NexNative)
- `copyToClipboard(text)` — write to Android clipboard from JS
- `readClipboard()` — read clipboard from JS
- `vibrate(ms)` — haptic feedback on interactions
- `getAppInfo()` — returns app name/version to plugins

## Build

```bash
./gradlew assembleDebug
# APK: app/build/outputs/apk/debug/app-debug.apk
```

## Package
`dev.nexcord.app`

## License
GPL-3.0 (inherited from Vencord)
