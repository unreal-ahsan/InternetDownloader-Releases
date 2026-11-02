# Third-party components and provenance

The original Internet Downloader code is MIT-licensed under LICENSE. That license does not relicense external runtimes or libraries. Retained notices are under `licenses/`; Go module versions are in `go.mod`, `go.sum` and [runtime-dependencies.json](docs/runtime-dependencies.json). Helper archives and exact digests are pinned in [helpers.lock.json](helpers.lock.json).

| Component | Use | License / provenance |
|---|---|---|
| Go 1.27.3 runtime/stdlib | Native application/installer | Go BSD-style notice retained |
| Walk + win | Native Windows controls/API | Upstream BSD notices retained |
| go-sqlite3 | SQLite CGO driver | MIT driver notice; SQLite retains its own public-domain status |
| golang.org/x/sys | Windows platform APIs | BSD-style notice retained |
| govaluate dependency | Walk dependency | Upstream notice retained; no user expression execution interface is exposed |
| Python 3.13.17 embeddable x64 | Stdio media inspector | PSF and bundled notices retained; official python.exe Authenticode verified Valid during acquisition |
| yt-dlp 2026.10.26 wheel | Supported-site extraction metadata | Upstream Unlicense/packaged notices retained; official PyPI SHA-256 verified |
| FFmpeg n8.1.3-32-g760d10603e-20261102, LGPL shared | Local-only stream-copy remux and test probing | LGPLv3 build; LGPL/GPLv3 texts retained; replaceable shared DLLs included |

FFmpeg is a separate helper executable; the application does not modify or statically link its libraries. Users can replace the compatible helper/DLLs. Exact upstream source is identified by [FFmpeg commit 760d10603e](https://github.com/FFmpeg/FFmpeg/tree/760d10603e); build/source recipes and dependency provenance are supplied by [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) and the pinned dated release. Source/build options and third-party codec/library obligations require review before public/commercial redistribution; this document does not certify that review or patent clearance. Keep the corresponding-source materials/offer compliant for your distribution method.

Playwright/Chrome for Testing, resource compiler, benchmark tooling and govulncheck are development-only. They are not bundled as application runtime dependencies.

WireGuard/OpenVPN clients are not bundled. Connection management invokes supported official installed clients for user-authorized profiles; their own licenses apply. No user VPN profile or key is included in a distribution. Chrome/Edge/Brave names and platform APIs remain their owners' trademarks/services; no store approval or endorsement is claimed.

The manifest public key only stabilizes the unpacked companion ID. It is not a publicly trusted signature on the EXE/installer, and no signing certificate is bundled.
