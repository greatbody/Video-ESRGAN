# Video-ESRGAN
Automate video upscaling with Real-ESRGAN & FFmpeg – extract, enhance, and merge frames in one click.

## Prerequisites

### 1. Download realesrgan-ncnn-vulkan

You need to download the `realesrgan-ncnn-vulkan` executable from the official Real-ESRGAN repository:

**Download Link:** https://github.com/xinntao/Real-ESRGAN/releases

1. Go to the [Real-ESRGAN releases page](https://github.com/xinntao/Real-ESRGAN/releases)
2. Download the appropriate version for your operating system:
   - **Windows**
   - **macOS**
   - **Linux**
3. Extract the downloaded archive
4. Place the `realesrgan-ncnn-vulkan` executable and the `models` directory in the same directory as the `enlarge` script.

For more information about Real-ESRGAN, visit the [official repository](https://github.com/xinntao/Real-ESRGAN).

### 2. Install FFmpeg

FFmpeg is required for video processing (extracting frames, merging frames back to video).

#### Windows
- Download from [FFmpeg official website](https://ffmpeg.org/download.html)
- Or install via package manager:
  ```bash
  # Using Chocolatey
  choco install ffmpeg

  # Using Scoop
  scoop install ffmpeg
  ```

#### macOS
```bash
# Using Homebrew
brew install ffmpeg

# Using MacPorts
sudo port install ffmpeg
```

#### Linux
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install ffmpeg

# CentOS/RHEL/Fedora
sudo yum install ffmpeg
# or
sudo dnf install ffmpeg

# Arch Linux
sudo pacman -S ffmpeg
```

#### Verify Installation
After installation, verify that both tools are available:
```bash
ffmpeg -version
./realesrgan-ncnn-vulkan -h
```
