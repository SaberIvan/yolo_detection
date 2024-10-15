# YOLOv8 Real-Time Object Detection Using OpenCV

This project demonstrates how to use the YOLOv8 model in combination with OpenCV to perform real-time object detection on a video stream. The object detection results are visualized with bounding boxes and class labels, along with the frame rate (FPS) displayed on the output video.

## Table of Contents
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Explanation](#explanation)
- [License](#license)

## Requirements

To run this project, you need the following libraries and tools:

- Python 3.6+
- OpenCV
- Ultralytics' YOLOv8
- NumPy
- A webcam or video input source

## Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-repo/yolo-opencv-detection.git
   cd yolo-opencv-detection
   ```

2. **Install the necessary dependencies**:

   Run the following command to install the required Python packages:

   ```bash
   pip install opencv-python-headless numpy ultralytics
   ```

3. **Download YOLOv8 weights**:

   Before running the script, you need to download the YOLOv8 model weights:

   ```bash
   # This uses YOLOv8 medium model (yolov8m.pt)
   wget https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8m.pt
   ```

## Usage

1. **Run the object detection script**:

   ```bash
   python object_detection.py
   ```

   By default, the script will use your webcam as the video source. If you'd like to use a different video source, you can modify the `VIDEO_SOURCE` variable in the script (e.g., a video file or a different stream).

2. **Terminate the program**:

   Press the `q` key to stop the video stream and close the window.

## Explanation

- **Device selection**: The device used for computation can be changed based on your hardware. The default is set to `cpu`, but if you're using an M1 Mac, you can switch it to `"mps"` for GPU acceleration.

- **Video source**: The script uses OpenCV's `VideoCapture` to read from a video source. It can be a webcam (`0` for the default camera) or a video file (`'data/video.mp4'`).

- **YOLO model**: The script loads the YOLOv8 model using the Ultralytics package. The medium version of YOLOv8 (`yolov8m.pt`) is used in this example, but other variants (small, large, etc.) can also be used by specifying different weight files.

- **Confidence Threshold**: The `CONFIDENCE_THRESHOLD_LIMIT` is used to filter out detections with a low confidence score (less than 0.5). Only objects with higher confidence will be displayed.

- **Bounding boxes**: For each detection, a bounding box is drawn around the detected object. The color of the bounding box is dynamically changed based on the confidence level:
  - Confidence > 0.6: **Green**
  - 0.3 < Confidence ≤ 0.6: **Yellow**
  - Confidence ≤ 0.3: **Blue-purple**

- **FPS calculation**: The frame rate is calculated in real time, based on the time it takes to process each frame, and is displayed in the top left corner of the video.

## License

This project is licensed under the MIT License. You are free to use, modify, and distribute this project as needed.

---

Feel free to adapt this project to your specific needs and enjoy real-time object detection with YOLOv8!
