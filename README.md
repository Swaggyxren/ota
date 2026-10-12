# Unified OTA Repository for Tecno POVA 5 Pro 5G (`LH8n`)

Centralized Over-The-Air (OTA) update endpoint repository serving custom ROMs for the Tecno POVA 5 Pro 5G (`LH8n` / `MT6833P`).

---

## 1. Directory Structure & Endpoints

### AxionOS (`axion/`)
- **Wiring**: `lineage.updater.uri` in `lineage_LH8n.mk`
- **Endpoint Pattern**: `https://raw.githubusercontent.com/Swaggyxren/ota/main/axion/OTA/{variant}/{device}.json`
  - GMS Builds: [`axion/OTA/GMS/LH8n.json`](axion/OTA/GMS/LH8n.json)
  - Vanilla Builds: [`axion/OTA/VANILLA/LH8n.json`](axion/OTA/VANILLA/LH8n.json)

### Lunaris AOSP (`lunaris/`)
- **Wiring**: `UpdaterOverlay_LH8n` RRO overlay (`updater_server_url`)
- **Endpoint Pattern**: `https://raw.githubusercontent.com/Swaggyxren/ota/main/lunaris/builds/{device}.json`
  - GMS Builds: [`lunaris/builds/LH8n.json`](lunaris/builds/LH8n.json)
  - Vanilla Builds: [`lunaris/builds/vanilla/LH8n.json`](lunaris/builds/vanilla/LH8n.json)
  - Changelog: [`lunaris/changelogs/LH8n.txt`](lunaris/changelogs/LH8n.txt)

### Project Infinity-X (`infinity-x/`)
- **Wiring**: `UpdaterOverlay_LH8n` RRO overlay (`com.infinity.updater`) or `ro.infinity.updater.uri`
- **Endpoint Pattern**: `https://raw.githubusercontent.com/Swaggyxren/ota/main/infinity-x/gapps/{device}.json`
  - Gapps Builds: [`infinity-x/gapps/LH8n.json`](infinity-x/gapps/LH8n.json)
  - Vanilla Builds: [`infinity-x/vanilla/LH8n.json`](infinity-x/vanilla/LH8n.json)
  - Changelog: [`infinity-x/changelog/LH8n.txt`](infinity-x/changelog/LH8n.txt)

---

## 2. Release Instructions

1. Compile the target ROM (`m bacon` or target zip command).
2. Upload the flashable ZIP to GitHub Releases or SourceForge.
3. Update the corresponding `{device}.json` file with:
   - `datetime` / `timestamp`: Matching `ro.build.date.utc`
   - `filename`: Matching build zip filename
   - `size`: Exact byte length
   - `download` / `url`: Direct download URL
   - `md5` / `sha256`: Package checksums
4. Commit and push directly to `main`.
