# Dynamic Rembg Video Processor

This project demonstrates a pipeline to process videos by removing the background from a foreground video and overlaying it on a background video. The main steps involve extracting frames from the videos, removing the background from the foreground frames, overlaying the processed foreground frames on the background frames, and finally merging the frames back into a video.

## Features

- Extract frames from video files using FFmpeg.
- Remove the background from each frame of the foreground video using the `rembg` library.
- Overlay the processed foreground frames on the corresponding background frames.
- Combine the processed frames into a final output video using FFmpeg.

## Requirements

- Python 3.7 or higher
- FFmpeg
- Libraries: `tqdm`, `PIL` (Pillow), `rembg`, `numpy`, `opencv-python`

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/dynamic-rembg-video-processor.git
    cd Background_replacement_with_audio.ipynb
    ```

2. Install the required Python libraries:
    ```sh
    pip install requirements (above mentioned)
    ```

3. Ensure FFmpeg is installed on your system and is accessible via the command line. You can download it from [FFmpeg's official website](https://ffmpeg.org/download.html).

## Usage

1. Place your foreground and background video files in the `input videos` directory. Update the paths in the script if necessary.
2. Adjust the `fps` variable in the script to match the frame rate of your videos if needed.
3. Run the script:
    ```sh
    Run each Jupiter cell to obtain output
    ```

### Script Overview

- **extract_frames(video_path: str, output_directory: str, fps: int) -> bool**:
    Extracts frames from the specified video and saves them in the specified directory at the given frames per second (fps).

- **remove_background(image_path: str) -> Image.Image**:
    Removes the background from an image using the `rembg` library.

- **overlay_images(fg_image: Image.Image, bg_image: Image.Image) -> Image.Image**:
    Overlays the foreground image onto the background image, resizing the foreground to match the background dimensions.

### Pipeline

1. **Extract Frames**: Frames are extracted from the foreground and background videos and saved in temporary directories.
2. **Remove Background**: The background is removed from each frame of the foreground video.
3. **Combine Frames**: The processed foreground frames are overlayed onto the background frames.
4. **Create Output Video**: The combined frames are merged back into a final video using FFmpeg.

## Example

Assuming you have `foreground_video.mp4` and `background_video.mp4` in the `input videos` directory, running the script will produce `output_video.mp4` in the project root directory.

## Cleanup

The script automatically cleans up temporary directories after processing is complete.
