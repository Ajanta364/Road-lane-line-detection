# Road-lane-line-detection

This project is a Road Lane Line Detection System using Python and OpenCV. The system processes images and videos to detect and highlight road lane lines. It uses computer vision techniques to identify lane boundaries and ensures lanes are marked distinctly for better visibility and safety.

## Features

- **Lane Detection in Images**: Detects lanes in individual images and highlights them.
- **Lane Detection in Videos**: Processes video frames to detect and highlight lanes in real-time.
- **Edge Detection**: Uses Canny edge detection to identify edges in the images.
- **Line Filtering**: Filters detected lines based on slope and length to eliminate false positives.
- **Line Averaging**: Averages multiple line segments to create a single line for each lane.
- **Temporal Consistency**: Maintains temporal consistency in video processing to reduce flickering of detected lines.
- **Customization Options**: Allows customization of various parameters such as kernel size, Canny thresholds, and more.

## Requirements

- Python 3.x
- OpenCV
- NumPy

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/road-lane-line-detection.git
   cd road-lane-line-detection
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Detect Lanes in Images

1. Place your test images in the `test_images` folder.
2. Run the following command:
   ```bash
   python detect_lanes_in_images.py
   ```
3. The processed images with detected lanes will be displayed.

### Detect Lanes in Videos

1. Place your test videos in the `test_videos` folder.
2. Run the following command:
   ```bash
   python detect_lanes_in_videos.py
   ```
3. The video with detected lanes will be displayed in real-time.

## Code Overview

### `detect_lanes(image, blur_kernel=9, canny_low=50, canny_high=150)`
- Converts the image to grayscale.
- Applies Gaussian blur to reduce noise.
- Detects edges using the Canny edge detector.

### `filter_lines(lines, threshold_slope, min_line_length, max_line_gap, roi_y)`
- Filters out lines based on their slope and length.
- Ensures lines are within the region of interest (ROI).

### `average_lines(lines, image_shape)`
- Averages the detected lines to create a single line for each lane.
- Splits lines into left and right based on their slope.
- Calculates the average line for each side.

### `draw_lines(image, lines, color=(0, 255, 0), thickness=8)`
- Draws the detected lines on a blank image.
- Combines the original image with the lines image using weighted addition.

### `process_image(image_path, threshold_slope=0.5, min_line_length=50, max_line_gap=100, roi_y=300)`
- Loads an image and processes it to detect lanes.
- Displays the resulting image with detected lanes.

### `process_video(video_path, threshold_slope=0.5, min_line_length=50, max_line_gap=100, roi_y=300)`
- Processes video frames to detect lanes in real-time.
- Maintains temporal consistency of detected lanes.

## Customization

You can customize various parameters in the functions to improve lane detection based on your specific requirements. Some of the parameters you can adjust include:
- `blur_kernel`: Size of the Gaussian blur kernel.
- `canny_low`, `canny_high`: Thresholds for Canny edge detection.
- `threshold_slope`: Minimum slope for a line to be considered a lane.
- `min_line_length`: Minimum length of a line to be considered.
- `max_line_gap`: Maximum allowed gap between line segments to treat them as a single line.
- `roi_y`: Y-coordinate for the region of interest.

## Example output

![Screenshot (92)](https://github.com/Ajanta364/Road-lane-line-detection/assets/174923401/6da2c0e1-aa32-4b03-97c6-950473e15950)

![Screenshot (91)](https://github.com/Ajanta364/Road-lane-line-detection/assets/174923401/c1849f29-1f36-44a8-b08c-2d789bc08dc6)
