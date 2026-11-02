# Internet Downloader

A native Windows download manager with segmented downloads, resume, video quality selection and a browser companion.

**[Download the latest release](https://github.com/unreal-ahsan/InternetDownloader-Releases/releases/latest)**

| File | Use |
|---|---|
| `InternetDownloader-Setup-0.2.0-unsigned.exe` | Installer for Windows x64 |
| `InternetDownloader-0.2.0-portable.zip` | Portable version, no install needed |
| `InternetDownloader-Chromium-0.2.0.zip` | Browser companion for Chrome, Edge and Brave |

Check your download against `SHA256SUMS.txt`.

## Features

- Up to eight connections per download, with resume after interruptions
- Download button on video pages, with a quality list right under it
- Run 1 to 8 downloads at once, with priorities, schedules, pause and resume
- HLS and DASH video assembly, including separate video and audio tracks
- WireGuard and OpenVPN profiles through the official clients
- SHA-256 verification; existing files are never overwritten

## Install

1. Run the installer, or extract the portable ZIP.
2. In `chrome://extensions`, turn on Developer mode, choose **Load unpacked**, and pick the `extension` folder inside the install folder. The installer has already connected the browser; portable users also click **Browser → Connect browser** in the app.
3. Click the extension icon and turn on **Show Download button on videos**.

## Good to know

- **The installer is unsigned.** Windows SmartScreen will warn you. Check the SHA-256 sum first.
- **The browser companion is not in any store.** It loads as an unpacked extension.
- **Not supported:** DRM-protected video, live streams, and sites that need a sign-in the app cannot see. The app never reads browser cookies.
- **VPN:** WireGuard profiles route only this app, leaving the rest of the PC on its normal connection. This was confirmed with one Proton WireGuard profile by comparing exit addresses. It has not been checked with packet capture, so check your own IP before relying on it. A VPN does not make you anonymous.

Download only content you have the right to download.

## License

The application is MIT-licensed. Bundled components keep their own licenses, listed in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) with full texts in [licenses/](licenses/).
