# WEBMARIZER

![](https://i.imgur.com/3PQKmFq.png)


## What is it?

Webmarizer is a GUI wrapper for FFmpeg.

## Dependencies

The application expects `ffmpeg` and `ffprobe` to be available. Bundled
binaries are used when present; otherwise, the system versions on your `PATH`
are executed. On macOS the application also checks common Homebrew locations
like `/opt/homebrew/bin` so Apple Silicon users with default installations are
picked up automatically. Install FFmpeg separately (e.g. `brew install ffmpeg`)
if you encounter errors about missing executables.

## What does it do?

One click - multiple GIFS or WEBMs from a single video.

![](https://i.imgur.com/cFoMwoj.gif)

WEBMARIZER automatically 'summarizes' a video by creating multiple WEBMs / GIFs per video in your folder. This is similar to a video thumbnails sheet but in GIF/WEBM form. Videos must be located in same folder that the program is in. 

## Features
- Automatically creates multiple GIFs or WEBMs with a single button click
- Lets you choose how many GIFs or WEBMs you want to create per video 
- Allows you to set limits on file size and width for both WEBMs and GIFs to comply with website limits (4chan, reddit, tumblr, etc)
- Allows you to enable or disable audio for WEBMs
- Lets you choose specific times / timestamps from which to generate GIFs or WEBMs
- Add custom text overlays to GIFs with configurable size, position, colour and transparency
- Uses VideoToolbox hardware acceleration on macOS when available
- Modernised interface styled via a Qt Style Sheet (`style.qss`)

## Text overlay

Use the text overlay fields in the General tab to caption GIFs. Set the
message, font size, X/Y position, colour (name or hex) and transparency
percentage before clicking **Create**.

## Where do I get it?

Go to the releases section [here](https://github.com/nyavramov/WEBMARIZER/releases) and download the latest release for Mac OSX or Windows.

### Building for Apple Silicon

When packaging on an Apple Silicon Mac, pass `--target-arch arm64` to
PyInstaller and bundle arm64 FFmpeg binaries:

```
sudo pyinstaller -F --target-arch arm64 --add-data 'ffmpeg:.' --add-data 'ffprobe:.' webmarizer.py
```
