# ClipSync Cloud — Binary Releases & Official Setup Guide

[![Release](https://img.shields.io/github/v/release/TheMich157/clipsync-releases?color=00E5FF&label=Latest%20Version&style=for-the-badge)](https://github.com/TheMich157/clipsync-releases/releases/latest)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011%20(x64)-blue?style=for-the-badge&logo=windows)](https://github.com/TheMich157/clipsync-releases/releases/latest)
[![License](https://img.shields.io/badge/Licensing-SellHidden%20Protected-emerald?style=for-the-badge)](https://clipsync-cloud.sellhidden.com/)
[![Client Zone](https://img.shields.io/badge/Client%20Zone-Self--Service%20Portal-purple?style=for-the-badge)](https://clipsync-website.onrender.com/client.html)

Official standalone distribution repository for **ClipSync Cloud** desktop client applications, release changelogs, and step-by-step configuration guides.

---

## ⚡ Direct Download

Download the verified standalone executable for Windows (64-bit):

| File | Version | Platform | Type | Link |
|---|---|---|---|---|
| **`ClipSyncCloud.exe`** | `v1.0.2` | Windows 10/11 (x64) | Standalone Single-File | [**Download Latest (v1.0.2)**](https://github.com/TheMich157/clipsync-releases/releases/latest/download/ClipSyncCloud.exe) |
| **All Releases & Tags** | All | Windows (x64) | Version Archive | [**View Release Archive**](https://github.com/TheMich157/clipsync-releases/releases) |

> [!NOTE]
> **Zero Dependencies**: ClipSync Cloud is compiled as a self-contained single-file binary. You do **not** need to install external .NET runtimes, Rclone, or third-party background drivers. Simply run `ClipSyncCloud.exe`.

---

## 📖 Complete Guide: How to Get What's Needed

Follow this quick step-by-step guide to get everything needed to run ClipSync Cloud:

### 1. Get Your License Key
To activate ClipSync Cloud on your PC, you need a unique license key formatted as `CSC-XXXX-XXXX-XXXX-XXXX`.

1. Visit our official storefront: [**ClipSync Cloud on SellHidden**](https://clipsync-cloud.sellhidden.com/) (or via the [Main Website](https://clipsync-website.onrender.com/#pricing)).
2. Select your preferred tier:
   - **Lifetime Access**: Permanent single payment ($4 base, or **$2 with 50% discount code `JQWOQ8`**).
   - **Monthly Pro / Yearly Pro**: Enhanced subscription tier with multi-PC concurrency (currently in **Pre-Order**).
3. Upon purchase, your license key is generated immediately on SellHidden and delivered to your email.
4. **Already bought?** Sign in anytime to the [**Client Zone**](https://clipsync-website.onrender.com/client.html) with your Discord account to see all your active and historical license keys, bound devices, and support tickets.

---

### 2. Download and Run the Desktop App
1. Download [**`ClipSyncCloud.exe`**](https://github.com/TheMich157/clipsync-releases/releases/latest/download/ClipSyncCloud.exe).
2. Move `ClipSyncCloud.exe` to a permanent location on your PC (e.g. `C:\Program Files\ClipSyncCloud` or `C:\Tools\ClipSyncCloud`).
3. Double-click to launch. ClipSync Cloud runs quietly in your Windows system tray.
4. On first startup, the activation window will appear. Enter your `CSC-XXXX-XXXX-XXXX-XXXX` license key and click **Activate**.

---

### 3. Get Your Google Drive Credentials (OAuth Client ID & Secret)
ClipSync Cloud uploads your gaming clips **directly from your PC to your private Google Drive**. Your clips never pass through any middleman servers, giving you 100% privacy and zero recurring cloud hosting fees.

You can connect in either of two ways:

#### Option A: 1-Click Browser Login (Recommended)
1. In the ClipSync Cloud desktop app, navigate to **Settings > Google Drive**.
2. Click **Connect Google Account**.
3. A secure browser window opens via Google OAuth2 Loopback. Sign in to your Google Account and click **Allow**.
4. The application receives the local auth token securely and confirms: `Connected to Google Drive`.

#### Option B: Use Your Own Google Cloud OAuth Credentials (Custom API Project)
If you prefer your own dedicated Google Cloud API quota:
1. Go to the [**Google Cloud Console**](https://console.cloud.google.com/).
2. Click **Select a project** > **New Project**, name it `ClipSync` and click **Create**.
3. In the left sidebar, navigate to **APIs & Services > Library**.
4. Search for **Google Drive API** and click **Enable**.
5. Go to **APIs & Services > OAuth consent screen**:
   - Choose **External** and click **Create**.
   - Enter an App name (`ClipSync`) and your email address.
   - Under **Test users**, add your own Google email address.
   - Save and continue.
6. Go to **APIs & Services > Credentials**:
   - Click **+ Create Credentials** > **OAuth client ID**.
   - Select **Application type: Desktop app**.
   - Name it `ClipSync Desktop` and click **Create**.
7. Google will display your **Client ID** and **Client Secret**.
8. Copy and paste both into ClipSync Cloud under **Settings > Google Drive > Custom Credentials**, then click **Save & Authenticate**.

---

### 4. Configure Medal.tv Clips Directory
1. Open your **Medal.tv** desktop app.
2. Go to **Settings (Gear icon) > Recorder > Capture Folder**.
3. By default, Medal stores clips at:
   ```text
   C:\Users\<YourUsername>\Videos\Medal
   ```
4. ClipSync Cloud automatically detects this directory on launch. If you have moved your Medal clips to another drive (e.g., `D:\Clips\Medal`), open ClipSync Cloud > **Settings > Watch Directory** and select your custom folder.
5. ClipSync Cloud monitors this folder in the background. As soon as you clip a gaming highlight, ClipSync Cloud detects the `.mp4` file, parses the game name and date, and uploads it to Google Drive into:
   ```text
   Google Drive / ClipSyncCloud / <GameName> / <YYYY-MM-DD> / clip.mp4
   ```

---

### 5. Multi-PC Device Licensing & Unbinding
- **Hardware Binding**: Each license binds simultaneously to your PC's Hardware ID (HWID) and BIOS UUID.
- **Allowed Devices**:
  - **Lifetime Plan**: Valid on up to **2 PCs concurrently** (e.g., your gaming desktop and streaming laptop).
  - **Pro Plans**: Valid on up to **5 PCs concurrently**.
- **Moving to a New PC**:
  If you buy a new computer or reinstall Windows, simply open the [**Client Zone**](https://clipsync-website.onrender.com/client.html), log in with Discord, find your device under **Activations**, and click **Unbind**. The activation slot frees up instantly so you can activate your new machine.

---

### 6. Local Disk Auto-Cleanup Engine
Running low on SSD space? ClipSync Cloud includes a safe, verified local cleanup engine:
1. When enabled in **Settings > Storage Cleanup**, clips older than 24 hours are evaluated for deletion.
2. **Double-Check Protection**: ClipSync Cloud queries Google Drive API, confirming the remote file exists, matches the byte count, and has a verified MD5 checksum.
3. Only after remote verification succeeds is the local file safely purged from your SSD.

---

## 🛠️ System Requirements

| Specification | Minimum | Recommended |
|---|---|---|
| **Operating System** | Windows 10 (64-bit, Build 19041+) | Windows 11 (64-bit) |
| **Architecture** | x64 (AMD64 / Intel 64) | x64 |
| **RAM** | 256 MB free | 512 MB |
| **Disk Space** | 150 MB (for binary) | 200 MB |
| **Network** | Broadband internet connection | High-speed fiber (for 4K clip uploads) |
| **Account** | Free Google Account (15 GB free Drive storage) | Google One storage plan if storing 100+ GB |

---

## 🔒 Security & Privacy Architecture

- **No Remote Key Logging**: License verification uses SHA-256 HMAC digital signatures.
- **No Third-Party Clip Servers**: All video uploads travel directly from your computer to `https://www.googleapis.com/upload/drive/v3/files` over TLS 1.3.
- **Zero Telemetry on Video Content**: ClipSync Cloud only checks license heartbeats; your gaming videos, audio, and personal files are never sent to ClipSync Cloud servers.

---

## 💬 Support & Community

- **Client Portal**: [https://clipsync-website.onrender.com/client.html](https://clipsync-website.onrender.com/client.html)
- **Storefront**: [https://clipsync-cloud.sellhidden.com/](https://clipsync-cloud.sellhidden.com/)
- **Main Website**: [https://clipsync-website.onrender.com/](https://clipsync-website.onrender.com/)
- **Documentation & Setup Guides**: [https://clipsync-website.onrender.com/guides.html](https://clipsync-website.onrender.com/guides.html)
- **Discord Community**: Open support tickets and chat with developers directly in our Discord server.
