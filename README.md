# Maestro Mobile Testing Project

Automated mobile UI testing for Google Maps using Maestro framework.

##  Quick Start

### Prerequisites
- Maestro installed (`curl -Ls "https://get.maestro.mobile.dev" | bash`)
- Android SDK Platform Tools (ADB)
- Android Emulator or physical device
- Google Maps installed on device

### Installation

1. Install Maestro:
   ```bash
   curl -Ls "https://get.maestro.mobile.dev" | bash
   ```

2. Install Android Platform Tools (macOS):
   ```bash
   brew install --cask android-platform-tools
   ```

3. Clone this repository

### Running Tests

```bash
# Run all tests
./run-tests.sh all

# Run specific test
./run-tests.sh basic-launch
./run-tests.sh coordinate-search

# Run directly with Maestro
maestro test google-maps/tests/basic-launch.yaml
maestro test google-maps/tests/coordinate-based-search.yaml
```

## 📁 Project Structure

```
Maestro/
├── google-maps/
│   ├── config.yaml                      # Maestro configuration
│   └── tests/
│       ├── basic-launch.yaml            # Simple app launch test
│       └── coordinate-based-search.yaml # Location search test
├── run-tests.sh                         # Test execution script
└── README.md                            # This file
```

## 🧪 Test Cases

### 1. Basic Launch
**File**: `basic-launch.yaml`  
**Purpose**: Verify Google Maps launches successfully  
**Tags**: `smoke`, `launch`

**Steps**:
- Set location to Melbourne CBD
- Launch Google Maps with clear state
- Wait for app to load
- Capture screenshot

### 2. Coordinate-Based Search
**File**: `coordinate-based-search.yaml`  
**Purpose**: Test search functionality using coordinate tapping  
**Tags**: `search`, `functional`

**Steps**:
- Launch Google Maps
- Tap on search bar (using coordinates for better compatibility)
- Enter "Docklands Melbourne"
- Submit search
- Verify results loaded and capture screenshot

## 🛠️ Test Results & Debugging

Test artifacts (screenshots, logs) are automatically saved in:
```
~/.maestro/tests/<timestamp>/
```

**Note**: Screenshots and test artifacts are excluded from git via `.gitignore` to keep the repository clean.

Each test run creates a new directory with:
- Screenshots at key points
- Maestro execution logs
- UI hierarchy dumps
- AI analysis reports (if enabled)

## 📊 Current Status

✅ **All tests passing (2/2)**

## 🔧 Configuration

- **App ID**: `com.google.android.apps.maps`
- **Default Device**: `emulator-5554`
- **Test Location**: Melbourne CBD (-37.8136, 144.9631)

## � Best Practices

- Tests use **coordinate-based tapping** instead of element IDs for better compatibility across different Google Maps versions
- All tests include **location setup** for consistent results
- **Screenshots are captured** at key points for debugging
- Tests use **clearState** to ensure clean starting conditions
- **Waits and timeouts** are included to handle loading states

## 🎯 Useful Commands

### Device Management
```bash
# List connected devices
adb devices

# Start emulator
emulator -avd <device_name>
```

### App Management
```bash
# Check if Google Maps is installed
adb shell pm list packages | grep maps

# Clear app data
adb shell pm clear com.google.android.apps.maps
```

### Maestro Debugging
```bash
# Run with verbose output
maestro test --debug-output google-maps/tests/basic-launch.yaml

# Record test execution
maestro test --record google-maps/tests/coordinate-based-search.yaml
```

## 🤝 Contributing

This project demonstrates clean, maintainable mobile test automation. Feel free to add more test cases following the same patterns.

## 📚 Resources

- [Maestro Documentation](https://maestro.mobile.dev/)
- [Maestro API Reference](https://maestro.mobile.dev/api-reference/commands)
- [Maestro Best Practices](https://maestro.mobile.dev/best-practices/best-practices)
