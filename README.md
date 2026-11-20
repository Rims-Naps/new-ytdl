# Termux URL Share Downloader

A Bash-based URL-share downloader for the GitHub build of Termux on Android.

The repository contains `termux-url-opener`, invoked by Android's share sheet,
and `install.sh`, which installs dependencies and the opener.

## Install

Run this in the GitHub build of Termux:

```bash
cd "$HOME"
wget --no-check-certificate "https://raw.githubusercontent.com/Rims-Naps/new-ytdl/refs/heads/main/install.sh"
chmod +x install.sh
bash install.sh
```

The installer preserves existing yt-dlp and downloader configuration.

## Configuration

Create `~/.config/termux-yt-dlg/config` with any of these exact lines:

```text
NOTIFICATIONS=true
RETRY_PROMPTS=true
BACKGROUND_DOWNLOAD=false
```

Values must be literal `true` or `false`. Defaults are shown above.

## Verification

```bash
bash -n termux-url-opener install.sh
```

Behavioral testing should use local mocks for yt-dlp and Termux:API commands;
never download live media during verification.
