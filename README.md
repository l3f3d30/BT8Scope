# BT 8-Channel Bluetooth Oscilloscope

Native Android application (Kotlin) connecting via Bluetooth Classic to an external 8-channel device, displaying real-time waveforms as stacked line charts.

## Features

- **Device Selection**: Browse and connect to paired Bluetooth devices
- **8-Channel Display**: Real-time waveform visualization with LineChart
- **Touch Controls**:
  - Center tap: Toggle RUN/STOP data collection
  - Top-right tap: Send CHECK command (0xF0)
  - Top-left tap: Disconnect and return to device list
- **Landscape-only** screen for optimal viewing
- **Bluetooth Protocol**: 16-byte packets (2 bytes/channel) with 0x00 0x00 delimiter

## Tech Stack

- Language: **Kotlin 100%**
- Platform: **Android 7.1+** (minSdk 25)
- Build: **Gradle** with Kotlin DSL
- UI: **Android Material Design** + **MPAndroidChart**
- Bluetooth: **Classic (RFCOMM/SPP)**

## Code Statistics

- DeviceListActivity.kt: 65 lines
- ScopeActivity.kt: 202 lines
- BluetoothHelper.kt: 130 lines
- **Total: 390+ lines** of production code

## Build APK

### Option 1: GitHub Actions (RECOMMENDED)

1. Fork this repository to your account
2. Push code to GitHub
3. GitHub Actions automatically builds APK
4. Download from Actions > Artifacts > app-release (~5-8 MB)

### Option 2: Build Locally

```bash
git clone https://github.com/<username>/BT8Scope
cd BT8Scope
./gradlew assembleRelease
```

APK location: `app/build/outputs/apk/release/app-release.apk`

## Installation

1. Enable "Unknown Sources" in Android Settings
2. Download APK to device
3. Open with file manager and tap to install
4. Grant permissions (Bluetooth, Location)

## Requirements

- Android 7.1+ device with Bluetooth Classic support
- External 8-channel device connected via Bluetooth serial (SPP profile)
- Permissions: BLUETOOTH, BLUETOOTH_ADMIN, ACCESS_FINE_LOCATION

## License

MIT

---

**Project Status**: Production-ready source code with GitHub Actions CI/CD workflow for APK building.
