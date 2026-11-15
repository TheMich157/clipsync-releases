# ClipSync Cloud — Step-by-Step Setup & Configuration Manual

This guide walks you through the initial configuration of **ClipSync Cloud** on Windows.

---

## 1. Prerequisites Checklist
Before you begin, ensure you have:
1. **Windows 10 or Windows 11 (64-bit)**.
2. A **Medal.tv** account and Medal Desktop App installed.
3. A **Google Account** (free 15 GB or Google One storage plan).
4. A **ClipSync Cloud License Key** (`CSC-XXXX-XXXX-XXXX-XXXX`) from [SellHidden](https://clipsync-cloud.sellhidden.com/) or the [Client Zone](https://clipsync-website.onrender.com/client.html).

---

## 2. Installation
1. Download the standalone executable: [`ClipSyncCloud.exe`](https://github.com/TheMich157/clipsync-releases/releases/latest/download/ClipSyncCloud.exe).
2. Place it in a folder where you have write permissions (e.g., `%LOCALAPPDATA%\Programs\ClipSyncCloud` or `C:\ClipSyncCloud`).
3. *(Optional)* Right-click `ClipSyncCloud.exe` > **Create Shortcut** and move the shortcut to your Windows Startup folder:
   - Press `Win + R`, type `shell:startup`, and press Enter. Paste the shortcut here to have ClipSync Cloud launch automatically on boot.

---

## 3. License Activation
1. Launch `ClipSyncCloud.exe`.
2. Enter your license key: `CSC-XXXX-XXXX-XXXX-XXXX`.
3. Click **Activate License**.
4. ClipSync Cloud authenticates with the cloud licensing server and binds your machine's HWID and BIOS UUID.
5. You will see a green badge: `● License Valid (Lifetime Pro / Active Subscription)`.

---

## 4. Google Drive Connection

ClipSync Cloud interacts directly with the Google Drive v3 REST API.

### Method 1: Easy OAuth Loopback
1. In ClipSync Cloud, click **Connect Google Drive**.
2. Your default web browser will open an official Google authorization page.
3. Select your Google account and grant permissions to create and manage files in Google Drive.
4. Once completed, your browser will show: `✓ Authentication Successful. You can close this window.`
5. ClipSync Cloud will update its status to `Connected to Google Drive`.

### Method 2: Custom Google Cloud Project (Advanced)
If you want completely independent API quotas:
1. Go to [Google Cloud Console](https://console.cloud.google.com).
2. Create project `ClipSync`.
3. Enable `Google Drive API`.
4. Create an OAuth 2.0 Client ID for `Desktop App`.
5. Enter your `Client ID` and `Client Secret` in ClipSync Cloud settings.

---

## 5. Medal.tv Clip Watcher Configuration
1. ClipSync Cloud will automatically scan for `C:\Users\<user>\Videos\Medal`.
2. When a match is found, status changes to `Monitoring Medal clips`.
3. Any new `.mp4` video written by Medal triggers an automated background upload into Google Drive under:
   `My Drive / ClipSyncCloud / <GameName> / <Date> / <FileName>.mp4`

---

## 6. Device Management & Moving Between PCs
- **Lifetime License**: Allows up to 2 PCs concurrently.
- **Pro Subscriptions**: Allows up to 5 PCs concurrently.
- To transfer a license to a new PC:
  1. Open [**Client Zone**](https://clipsync-website.onrender.com/client.html).
  2. Sign in with Discord.
  3. Under **Activations**, find the old machine.
  4. Click **Unbind Device**.
  5. The license slot is immediately available for activation on your new PC.
