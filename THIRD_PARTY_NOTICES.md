# Third-party components and provenance

The original Internet Downloader code is MIT-licensed under LICENSE. That license does not relicense external runtimes or libraries. Retained notices are under `licenses/`; Go module versions are in `go.mod`, `go.sum` and [runtime-dependencies.json](docs/runtime-dependencies.json). Helper archives and exact digests are pinned in [helpers.lock.json](helpers.lock.json).

| Component | Use | License / provenance |
|---|---|---|
| Go 1.27.3 runtime/stdlib | Native application/installer | Go BSD-style notice retained |
| Walk + win | Native Windows controls/API | Upstream BSD notices retained |
| go-sqlite3 | SQLite CGO driver | MIT driver notice; SQLite retains its own public-domain status |
| golang.org/x/sys | Windows platform APIs | BSD-style notice retained |
| wireguard-go + netstack | In-process WireGuard protocol and virtual network adapter | Upstream MIT license retained; pinned in go.mod/go.sum |
| gVisor | Private userspace TCP/IP stack | Apache-2.0 license and upstream notices retained |
| Microsoft go-winio | Current-user-only Windows named-pipe IPC | MIT license retained |
| golang.org/x/crypto, x/net, x/exp, x/time; google/btree | Cryptographic/networking/stack dependencies | Upstream BSD-style/Apache notices retained; pinned module inventory |
| wintun Go module | Transitive WireGuard interface package dependency | Upstream notice retained; no Wintun driver DLL is bundled, installed or opened for userspace sessions |
| govaluate dependency | Walk dependency | Upstream notice retained; no user expression execution interface is exposed |
| Python 3.13.17 embeddable x64 | Stdio media inspector | PSF and bundled notices retained; official python.exe Authenticode verified Valid during acquisition |
| yt-dlp 2026.10.26 wheel | Supported-site extraction metadata | Upstream Unlicense/packaged notices retained; official PyPI SHA-256 verified; the release adds bytecode for the bundled Python beside each unchanged source file (scripts/compile-library.py) |
| FFmpeg n8.1.3-32-g760d10603e-20261102, LGPL shared | Local-only stream-copy remux and test probing | LGPLv3 build; LGPL/GPLv3 texts retained; replaceable shared DLLs included |

FFmpeg is a separate helper executable; the application does not modify or statically link its libraries. Users can replace the compatible helper/DLLs. Exact upstream source is identified by [FFmpeg commit 760d10603e](https://github.com/FFmpeg/FFmpeg/tree/760d10603e); build/source recipes and dependency provenance are supplied by [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) and the pinned dated release. Source/build options and third-party codec/library obligations require review before public/commercial redistribution; this document does not certify that review or patent clearance. Keep the corresponding-source materials/offer compliant for your distribution method.

Playwright/Chrome for Testing, resource compiler, benchmark tooling and govulncheck are development-only. They are not bundled as application runtime dependencies.

The isolated WireGuard backend is compiled into the app. No official VPN client is required for new connections; existing clients are used only for explicit removal of old downloader-owned Windows tunnels. OpenVPN activation is disabled. No user VPN profile or key is included in a distribution. Chrome/Edge/Brave names and platform APIs remain their owners' trademarks/services; no store approval or endorsement is claimed.

The manifest public key only stabilizes the unpacked companion ID. It is not a publicly trusted signature on the EXE/installer, and no signing certificate is bundled.
