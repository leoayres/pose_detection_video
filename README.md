
# 🤖 Video Pose Detection

This project enables **real-time human pose estimation** from webcam or video files using **MediaPipe** and **OpenCV**.
It supports headless or GUI environments and provides live overlay of pose landmarks on video frames, as well as optional output recording.

---

## 🔧 Features

* Real-time pose detection from webcam or a video file
* **MediaPipe** for robust human pose estimation (33 pose landmarks)
* Frame-by-frame processing with **OpenCV**
* Progress bar support via **tqdm** for video processing
* Drawing of pose skeleton on top of frames
* Optional saving of annotated output video
* Compatible with both interactive and headless environments

---

## 🚀 Getting Started

### 📦 Installation

Install the necessary Python packages:

```bash
pip install opencv-python mediapipe tqdm
```

---

## ▶️ Usage

### 1. Run pose detection using webcam

```bash
python detect_pose.py --source webcam
```

### 2. Run on a video file

```bash
python detect_pose.py --source /path/to/video.mp4
```

### 3. Save the annotated output

```bash
python detect_pose.py --source /path/to/input.mp4 --output /path/to/output.mp4
```

---

## 🧩 How It Works

1. **Frame Capture**

   * OpenCV captures frames from webcam or video file using `cv2.VideoCapture`.

2. **Pose Estimation (MediaPipe)**

   * Each frame is passed to MediaPipe’s Pose model.
   * Returns 33 landmark points (e.g., shoulders, hips, knees, etc.).

3. **Drawing Pose Landmarks**

   * OpenCV is used to draw skeleton lines, joints, and landmarks on each frame.
   * Customization possible for color, thickness, and drawing style.

4. **Progress Bar**

   * `tqdm` shows progress when processing a video file.

5. **Output Handling**

   * Annotated frames are either displayed in real-time (if GUI) or processed headlessly.
   * If `--output` is provided, writes a new video file with pose annotations applied.

---


---

## 📈 Performance Tips

* Reduce frame resolution for faster processing
* Use a lower `model_complexity` in MediaPipe if performance is a concern
* For real-time webcam: skip drawing some landmarks or reduce drawing frequency
* If running on a server: consider headless mode to eliminate GUI overhead

---

## 🤝 Contributing

Contributions welcome!
Open an issue or submit a pull request to improve or extend functionality.

---

## 📜 License

This project is licensed under the **MIT License**.


