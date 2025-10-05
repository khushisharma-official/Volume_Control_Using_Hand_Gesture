# 🎵 Hand Gesture Volume Control

Control your system volume using hand gestures! This project uses computer vision and hand tracking to adjust your computer's volume by measuring the distance between your thumb and index finger.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.8+-green.svg)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0.10+-orange.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## 🎯 Features

- **Real-time Hand Tracking** - Detects hand landmarks using MediaPipe
- **Gesture-based Volume Control** - Pinch your fingers to adjust volume
- **Visual Feedback** - See real-time visualization of hand gestures
- **Distance Mapping** - Intuitive volume control based on finger distance
- **FPS Counter** - Monitor performance in real-time
- **Cross-platform** - Works on Windows (with Pycaw library)

[//]: # (## 🎥 Demo)

[//]: # ()
[//]: # (*&#40;Add a GIF or video demo here showing the volume control in action&#41;*)

[//]: # ()
[//]: # (![Demo GIF]&#40;demo.gif&#41;)

## 🛠️ Tech Stack

- **Python 3.8+** - Core programming language
- **OpenCV (cv2)** - Computer vision and video processing
- **MediaPipe** - Hand tracking and landmark detection
- **Pycaw** - Windows audio control
- **NumPy** - Numerical computations
- **cvzone** - Simplified computer vision operations

## 📋 Prerequisites

- Python 3.8 or higher
- Webcam
- Windows OS (for volume control functionality)

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/khushisharma-official/hand-gesture-volume-control.git
cd hand-gesture-volume-control
```

### 2. Create Virtual Environment (Recommended)

```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
python VolumeHandControl.py
```

## 📦 Requirements

Create a `requirements.txt` file with:

```txt
opencv-python==4.8.1.78
mediapipe==0.10.14
numpy==1.24.3
pycaw==20230407
comtypes==1.2.0
cvzone==1.6.1
```

## 🎮 How to Use

1. **Run the application** - Execute `VolumeHandControl.py`
2. **Position your hand** - Show your hand clearly to the webcam
3. **Control volume**:
   - Move your **thumb** and **index finger** closer together to decrease volume
   - Move them **apart** to increase volume
   - The distance between fingers maps to volume level (50-300 pixels range)
4. **Visual indicators**:
   - Purple circles show thumb and index finger positions
   - Line connects the two fingers
   - **Green circle** appears when volume is at minimum
   - Real-time volume level displayed on screen
5. **Exit** - Press any key to close the application

## 📁 Project Structure

```
hand-gesture-volume-control/
├── VolumeHandControl.py      # Main application
├── HandTrackingModule.py      # Hand detection module
├── requirements.txt           # Project dependencies
├── README.md                  # Project documentation
└── demo.gif                   # Demo video/GIF
```

## 🧩 Code Overview

### Main Components

**1. Hand Detection** (`HandTrackingModule.py`)
- Detects hands using MediaPipe
- Tracks 21 hand landmarks
- Provides hand position and landmark data

**2. Volume Control** (`VolumeHandControl.py`)
- Captures video from webcam
- Processes hand landmarks
- Calculates distance between thumb and index finger
- Maps distance to volume level using linear interpolation
- Controls system volume via Pycaw

### Key Functions

```python
# Hand detection
detector = htm.handDetector(detectionCon=0.7)
lmList = detector.findPosition(img, draw=False)

# Distance calculation
length = math.hypot(x2 - x1, y2 - y1)

# Volume mapping
vol = np.interp(length, [50, 300], [minVol, maxVol])
volume.SetMasterVolumeLevel(vol, None)
```

## ⚙️ Configuration

You can adjust these parameters in `VolumeHandControl.py`:

```python
# Camera resolution
wCam, hCam = 640, 480

# Hand detection confidence
detector = htm.handDetector(detectionCon=0.7)

# Finger distance range (adjust based on your preference)
vol = np.interp(length, [50, 300], [minVol, maxVol])
```

## 🐛 Troubleshooting

### Camera not working
- Ensure your webcam is connected and not being used by another application
- Check camera index in `cv2.VideoCapture(0)` - try changing to `1` or `2`

### Volume not changing
- Make sure you're running on Windows
- Check if Pycaw is properly installed: `pip install pycaw`
- Verify audio drivers are up to date

### Hand not detected
- Ensure good lighting conditions
- Keep hand clearly visible to camera
- Adjust `detectionCon` parameter for better detection

### Import errors
- Reinstall dependencies: `pip install -r requirements.txt`
- Make sure virtual environment is activated

## 🎨 Customization Ideas

- Add volume mute gesture (e.g., closed fist)
- Support multiple hand gestures for different controls
- Add GUI for settings adjustment
- Integrate with media player controls
- Add gesture recording and playback
- Cross-platform support (macOS, Linux)

[//]: # (## 📸 Screenshots)

[//]: # ()
[//]: # (### Normal Operation)

[//]: # (*&#40;Add screenshot showing volume control&#41;*)

[//]: # ()
[//]: # (### Minimum Volume Indicator)

[//]: # (*&#40;Add screenshot showing green indicator&#41;*)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

[//]: # (## 📝 License)

[//]: # ()
[//]: # (This project is licensed under the MIT License - see the [LICENSE]&#40;LICENSE&#41; file for details.)

## 🙏 Acknowledgments

- [MediaPipe](https://mediapipe.dev/) - For hand tracking technology
- [Pycaw](https://github.com/AndreMiras/pycaw) - For Windows audio control
- [OpenCV](https://opencv.org/) - For computer vision capabilities
- [cvzone](https://github.com/cvzone/cvzone) - For simplified CV operations

## 👨‍💻 Author

**Your Name**
- GitHub: [@khushisharma-official](https://github.com/khushisharma-official)
- LinkedIn: [Your Name](https://linkedin.com/in/khushi-sh)

[//]: # (- Portfolio: [yourwebsite.com]&#40;https://yourwebsite.com&#41;)
[//]: # (- Email: your.email@example.com)

## 🌟 Show your support

Give a ⭐️ if this project helped you!

[//]: # (## 📞 Contact)

[//]: # ()
[//]: # (For any queries or suggestions, feel free to reach out:)

[//]: # (- Open an issue on GitHub)

[//]: # (- Email: your.email@example.com)

[//]: # ()
[//]: # (---)

[//]: # ()
[//]: # (**Made with ❤️ and Python**)