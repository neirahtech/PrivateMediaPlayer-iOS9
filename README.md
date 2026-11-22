# Private Media Player (iOS 9+)

An Objective-C starter Xcode project for an offline, PIN-gated media library.

## Included
- First-run 4- or 6-digit PIN setup; subsequent launch requires the PIN. PIN is stored in the iOS Keychain.
- Local media browser for MP4/M4V/MOV videos and JPG/JPEG/PNG photos.
- AVPlayer playback with play/pause, seek bar, elapsed/total time, previous/next and 10-second skip controls.
- Resolution selector for pre-encoded variants: Original, 360p, 480p, 720p and 1080p.
- iTunes File Sharing enabled, so 3uTools can add files to the app's Documents folder.
- Minimum deployment target set to iOS 9.0.

## Import with 3uTools
1. Install the signed app on the iPhone.
2. Open 3uTools and connect the iPhone.
3. Go to Apps, select **Private Media Player**, then open **File Sharing** (wording may vary by 3uTools version).
4. Add MP4/M4V/MOV and image files.
5. In the app, tap Refresh if the library was already open.

Recommended video: MP4 container, H.264 video, AAC audio, 1280x720 (720p). iOS 9 does not natively support HEVC/H.265 playback on all devices.

## Resolution switching
The selector switches between separately encoded files; it does not transcode a video. For a source named `Holiday.mp4`, add files with these exact names in the same Documents folder:
- `Holiday_360p.mp4`
- `Holiday_480p.mp4`
- `Holiday_720p.mp4`
- `Holiday_1080p.mp4`

Only available variants can be selected. The selected file is played directly.

## Build and install
A real iOS build/signature requires macOS with Xcode and an Apple signing identity/provisioning profile. This source package cannot produce a signed IPA on a Windows/Linux computer.

1. Open `PrivateMediaPlayer.xcodeproj` in Xcode on a Mac.
2. Select the `PrivateMediaPlayer` target.
3. Set your Team under **Signing & Capabilities** and change the bundle identifier if needed.
4. Confirm **iOS Deployment Target = 9.0**.
5. Choose a connected device or **Any iOS Device (arm64)** and build/archive.
6. Export a signed IPA, then install it using 3uTools.

## Important security note
This starter uses a PIN gate and Keychain storage for the PIN. It does **not** encrypt the media files themselves. Anyone with direct access to the app's Documents container may be able to copy the media. Do not treat this starter as a high-security encrypted vault.

## Compatibility note
The UI and APIs are intentionally kept to APIs available on iOS 9. Actual playback depends on the iPhone model and the media's codec/profile/level. Test on the target iPhone before distributing.
