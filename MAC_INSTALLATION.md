# 🍎 Rat Flipper Pro - Mac Installation Guide

## Prerequisites

### 1. Install Python 3.8+ (if not already installed)
```bash
# Using Homebrew (recommended)
brew install python3

# Or download from python.org
# https://www.python.org/downloads/macos/
```

### 2. Install Homebrew (if not already installed)
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Installation Steps

### 1. Clone or Download the Project
```bash
# If using git
git clone <repository-url>
cd ratflipper-project

# Or download and extract the ZIP file
```

### 2. Create a Virtual Environment (Recommended)
```bash
# Create virtual environment
python3 -m venv ratflipper_env

# Activate virtual environment
source ratflipper_env/bin/activate
```

### 3. Install Dependencies
```bash
# Install required packages
pip3 install -r requirements_mac.txt

# Or install manually:
pip3 install customtkinter>=5.2.0
pip3 install aiofiles>=23.2.1
pip3 install aiohttp>=3.9.1
pip3 install nats-py>=2.6.0
pip3 install pandas>=2.1.4
pip3 install numpy>=1.24.0
pip3 install watchdog>=3.0.0
pip3 install requests>=2.31.0
pip3 install Pillow>=10.1.0
```

### 4. Optional: Install Mac-Specific Optimizations
```bash
# For better Mac integration (optional)
pip3 install pyobjc-framework-Cocoa>=10.0
pip3 install pyobjc-framework-Quartz>=10.0
```

## Running the Application

### 1. Prepare Your Items File
Create an `items.txt` file in the same directory as the script with your items:
```
T4_2H_BOW
T5_2H_BOW
T6_2H_BOW
```

### 2. Run the Application
```bash
# Make sure virtual environment is activated
source ratflipper_env/bin/activate

# Run the application
python3 "Ratflipper (2).py"
```

## Mac-Specific Features

### ✅ What Works on Mac:
- **Full GUI functionality** with CustomTkinter
- **Cross-platform sound notifications** using macOS system sounds
- **File monitoring** for items.txt changes
- **NATS connection** for real-time market data
- **All analytics and flip detection features**
- **Modern notification system** with slide animations
- **Background image support**

### 🎵 Sound System:
- Uses macOS system sounds (`afplay`)
- Notification sounds: `/System/Library/Sounds/Glass.aiff`
- Button click sounds: `/System/Library/Sounds/Tink.aiff`

### 📁 File Paths:
- Uses standard Unix file paths
- Compatible with macOS file system
- Supports relative and absolute paths

## Troubleshooting

### Common Issues:

#### 1. "Permission Denied" Error
```bash
# Fix file permissions
chmod +x "Ratflipper (2).py"
```

#### 2. CustomTkinter Not Found
```bash
# Reinstall CustomTkinter
pip3 uninstall customtkinter
pip3 install customtkinter>=5.2.0
```

#### 3. Sound Not Working
```bash
# Check if afplay is available
which afplay

# Test sound manually
afplay /System/Library/Sounds/Glass.aiff
```

#### 4. Python Version Issues
```bash
# Check Python version
python3 --version

# Should be 3.8 or higher
```

### Performance Tips:

1. **Use Virtual Environment**: Keeps dependencies isolated
2. **Close Other Apps**: Free up memory for better performance
3. **Monitor Activity**: Check Activity Monitor for resource usage
4. **Update Python**: Use the latest Python 3.x version

## Creating a Mac App Bundle (Optional)

### Using py2app:
```bash
# Install py2app
pip3 install py2app

# Create setup.py
echo 'from setuptools import setup
APP = ["Ratflipper (2).py"]
OPTIONS = {
    "argv_emulation": True,
    "packages": ["customtkinter", "aiofiles", "aiohttp", "nats", "pandas", "watchdog", "requests", "PIL"],
    "iconfile": "icon.icns"  # if you have an icon
}
setup(
    app=APP,
    options={"py2app": OPTIONS},
    setup_requires=["py2app"],
)' > setup.py

# Build the app
python3 setup.py py2app
```

## Support

If you encounter any issues:
1. Check the console output for error messages
2. Ensure all dependencies are installed correctly
3. Verify Python version compatibility
4. Check file permissions and paths

## System Requirements

- **macOS**: 10.14 (Mojave) or later
- **Python**: 3.8 or higher
- **RAM**: 4GB minimum, 8GB recommended
- **Storage**: 100MB free space
- **Network**: Internet connection for NATS data

---

**Note**: This app is designed to work seamlessly on macOS with full feature parity to the Windows version. All animations, notifications, and real-time features are fully functional on Mac.
