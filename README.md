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

## Usage

### Basic Usage
To enhance a video, simply run the `enlarge` script with your input video file:

```bash
./enlarge input_video.mp4
```

### What the Script Does
1. **Extracts frames** from your input video using FFmpeg
2. **Enhances each frame** using Real-ESRGAN with the `realesr-animevideov3` model (2x upscaling)
3. **Merges enhanced frames** back into a new video while preserving the original audio

### Output
The script generates:
- **Enhanced video**: `enhanced_YYYYMMDD_HHMMSS.mp4` - Your upscaled video
- **Temporary folders**:
  - `tmp_frames_YYYYMMDD_HHMMSS/` - Original extracted frames
  - `out_frames_YYYYMMDD_HHMMSS/` - Enhanced frames

### Features
- ✅ **Progress tracking** with real-time progress bar and ETA
- ✅ **Automatic framerate detection** from source video
- ✅ **Audio preservation** - copies original audio to enhanced video
- ✅ **Unique timestamped outputs** - prevents file conflicts
- ✅ **Error handling** with detailed feedback
- ✅ **Processing statistics** - shows total time and frames processed

### Example
```bash
# Make the script executable (first time only)
chmod +x enlarge

# Enhance a video
./enlarge my_video.mp4

# Output will be something like:
# enhanced_20241224_143052.mp4
```

### Tips
- The script uses the `realesr-animevideov3` model which works well for anime/cartoon content
- Processing time depends on video length, resolution, and your hardware
- You can safely delete the temporary frame folders after processing
- For best results, ensure your input video has good quality (not heavily compressed)

## Example Files

Check the `example/` directory for sample input and output files to test the script.
