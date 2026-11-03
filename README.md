# Internet Downloader

A native Windows download manager with segmented downloads, resume, video quality selection and a browser companion.

**[Download the latest release](https://github.com/unreal-ahsan/InternetDownloader-Releases/releases/latest)**

| File | Use |
|---|---|
| `InternetDownloader-Setup-0.2.6-unsigned.exe` | Installer for Windows x64 |
| `InternetDownloader-0.2.6-portable.zip` | Portable version, no install needed |
| `InternetDownloader-Chromium-0.2.6.zip` | Browser companion for Chrome, Edge and Brave |

Check your download against `SHA256SUMS.txt`.

## Features

- Up to eight connections per download, with resume after interruptions
- Expired video links are renewed for the same quality, and large videos continue from the last saved piece
- Download button on video pages, with a quality list right under it; drag it out of the way and it stays put on that site
- Run 1 to 8 downloads at once, with priorities, schedules, pause and resume
- HLS and DASH video assembly, including separate video and audio tracks
- Built-in WireGuard VPN for this app only, with no Windows adapter, service or route changes
- Optional browser sign-in for sites you approve one by one, such as Facebook; never used for YouTube or Google
- New downloads sorted into Videos, Audio, Images, Documents, Compressed, Programs and Other folders
- SHA-256 verification; existing files are never overwritten

## Install

1. Run the installer, or extract the portable ZIP.
2. In `chrome://extensions`, turn on Developer mode, choose **Load unpacked**, and pick the `extension` folder inside the install folder. The installer has already connected the browser; portable users also click **Browser → Connect browser** in the app.
3. Click the extension icon and turn on **Show Download button on videos**.

## Good to know

- **The installer is unsigned.** Windows SmartScreen will warn you. Check the SHA-256 sum first.
- **The browser companion is not in any store.** It loads as an unpacked extension.
- **Not supported:** DRM-protected video and live streams. The app reads a site's cookies only after you approve that site, only to find the video, and never stores them.
- **VPN:** WireGuard runs inside the app, so only its downloads use the VPN and the rest of the PC stays on its normal connection. Nothing VPN-related is installed into Windows. This was confirmed with one Proton WireGuard profile by comparing exit addresses; it has not been checked with packet capture. VPN downloads never fall back to your normal connection: if the tunnel is down, they pause. After you turn the VPN off yourself, resuming continues them on your normal connection. OpenVPN profiles can be imported but not connected yet. A VPN does not make you anonymous.

Download only content you have the right to download.

## License

The application is MIT-licensed. Bundled components keep their own licenses, listed in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) with full texts in [licenses/](licenses/).
