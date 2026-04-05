# Amanda-

An Objective-C library providing VoIP call context management for iOS and macOS applications.

## Overview

Amanda- exposes interfaces for managing ongoing calls, group calls, audio/video capture and rendering, and related signaling over WebRTC.

## Features

- **1-to-1 VoIP Calls** — `OngoingCallThreadLocalContextWebrtc` manages the full lifecycle of a peer-to-peer call including signaling, network type changes, mute/unmute, and video.
- **Group Calls** — `GroupCallThreadLocalContext` supports multi-participant audio/video calls with broadcast (HLS) fallback, noise suppression, and per-ssrc volume control.
- **Audio Device** — `SharedCallAudioDevice` provides a shared audio session that can be reused across calls, with manual activation and tone playback.
- **Video Capture** — `OngoingCallThreadLocalContextVideoCapturer` wraps device cameras and supports external pixel-buffer injection (e.g., screen capture).
- **Video Rendering** — `OngoingCallThreadLocalContextWebrtcVideoView` protocol for displaying remote and local video streams with orientation and mirroring support.
- **Proxy Support** — `VoipProxyServerWebrtc` for routing VoIP traffic through a proxy server.

## Requirements

- iOS 13+ / macOS 10.15+
- Xcode 14+

## Platform Notes

On **iOS**, the library uses `UIKit` and `CoreMedia` for video capture and rendering.  
On **macOS**, `AppKit` is used instead and `UIView` is aliased to `NSView`.

## Key Types

| Type | Description |
|---|---|
| `OngoingCallThreadLocalContextWebrtc` | Manages a single WebRTC-based VoIP call |
| `GroupCallThreadLocalContext` | Manages a multi-participant group call |
| `SharedCallAudioDevice` | Shared audio session / device |
| `OngoingCallThreadLocalContextVideoCapturer` | Camera / external video source |
| `CallAudioTone` | Audio tone (ringback, busy, etc.) |
| `OngoingCallConnectionDescriptionWebrtc` | STUN/TURN server descriptor |
| `VoipProxyServerWebrtc` | Proxy server configuration |
| `GroupCallDisposable` | Cancellable subscription handle |

## License

See [LICENSE](LICENSE) for details.