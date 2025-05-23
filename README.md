---

# Animotion - Real-Time Facial Tracker for Avatar Animation

Animotion is a **real-time facial tracking system** designed to capture facial expressions and head movements, enabling avatar animation. Using **OpenCV** and **MediaPipe**, Animotion detects facial landmarks and transmits data via **WebSocket** to applications like **VTube Studio**. The project now includes an advanced **deep-learning-based lip sync module (Wav2Lip-SD-NOGAN)** with optional audio capture for improved lip synchronization.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Download the Advanced Lip Sync Model](#download-the-advanced-lip-sync-model)
- [Usage](#usage)
- [Customization](#customization)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)
- [Contact](#contact)

---

## Features

✅ **Real-Time Facial Expression Detection** – Captures blinks, mouth movements, eyebrow raises, and lip sync  
✅ **Head Pose Estimation** – Tracks yaw, pitch, and roll movements  
✅ **Advanced Lip Sync Detection** – Uses deep learning (**Wav2Lip-SD-NOGAN**) for high-accuracy synchronization  
✅ **WebSocket Integration** – Sends real-time facial data to avatar applications  
✅ **Configurable Parameters** – Custom settings via the `config.ini` file  
✅ **Logging and Error Handling** – Comprehensive logs for robust performance  
✅ **Modular Design** – Clean structure for easy maintenance and expansion

---

## Prerequisites

- 🖥 **OS**: Windows, macOS, or Linux
- 🐍 **Python 3.7+**
- 🎥 **Webcam** (built-in or external)
- 🎙 **Microphone** (for advanced lip sync)
- 📦 **Virtual Environment** (recommended to prevent package conflicts)

---

## Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/RohanRajesh55/Animotion.git
cd Animotion
```

### 2️⃣ Create a Virtual Environment

```bash
python -m venv venv
```

### 3️⃣ Activate the Virtual Environment

**Windows**:

```bash
venv\Scripts\activate
```

**macOS/Linux**:

```bash
source venv/bin/activate
```

### 4️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

ℹ Ensure packages like `opencv-python`, `mediapipe`, `numpy`, `websockets`, `torch`, `librosa`, `soundfile`, `sounddevice`, etc., are installed.

---

## Configuration

Customize settings in **`config.ini`** for fine-tuned control. Example:

```ini
[Camera]
DROIDCAM_URL = 0  # Set 0 for default webcam

[Thresholds]
EAR_THRESHOLD = 0.22
MAR_THRESHOLD = 0.5
EBR_THRESHOLD = 1.5
EMOTION_THRESHOLD = 0.4

[WebSocket]
VTS_WS_URL = ws://localhost:8001
AUTH_TOKEN = your_auth_token

[Logging]
LOG_LEVEL = INFO  # Options: DEBUG, INFO, WARNING, ERROR, CRITICAL

[Animation]
SMOOTHING_FACTOR = 0.8
INTERPOLATION_TYPE = linear

[Advanced]
USE_DEEP_LIP_SYNC = True
AUDIO_SAMPLE_RATE = 16000
AUDIO_DEVICE_ID = 0
LIP_SYNC_SKIP_FRAMES = 3
MODEL_PATH = models/Wav2Lip-SD-NOGAN.pt
```

---

## Download the Advanced Lip Sync Model

To use **Wav2Lip-SD-NOGAN**, download the pre-trained model:

🔗 [Download Wav2Lip-SD-NOGAN Model](https://drive.google.com/drive/folders/153HLrqlBNxzZcHi17PEvP09kkAfzRshM)

### 📌 Instructions:

1. Click the link above.
2. Download `Wav2Lip-SD-NOGAN.pt`.
3. Move the file into the `models/` directory.
4. Adjust `MODEL_PATH` in `config.ini` if needed.

---

## Usage

### 🚀 Run the Application

```bash
python main.py
```

### 🎭 Interact with Animotion

- **Eye Blink Detection** – Blink your eyes
- **Mouth Open Detection** – Open your mouth
- **Lip Sync Test** – Speak or move lips (microphone required)
- **Head Pose Estimation** – Rotate head to test yaw/pitch/roll
- **Emotion Detection** – Placeholder (extendable)

### ❌ Quit the Application

Press **`q`** in the window to exit.

---

## Customization

### 🛠 Adjusting Thresholds

Modify `EAR_THRESHOLD`, `MAR_THRESHOLD`, `EBR_THRESHOLD`, etc., in `config.ini` for optimal tracking.

### 🖼 Modifying Components

- Refer to the [MediaPipe Face Mesh landmark map](https://google.github.io/mediapipe/solutions/face_mesh.html)
- Extend functionality by adding modules in the `detectors/` directory
- Customize avatar animation parameters in `websocket_client.py`

---

## Project Structure

```
Animotion/
├── main.py               # Main facial tracking script
├── config.ini            # Configuration settings
├── requirements.txt      # Dependencies list
├── websocket_client.py   # WebSocket integration
├── detectors/            # Modules for feature detection
│   ├── eye_detector.py
│   ├── mouth_detector.py
│   ├── eyebrow_detector.py
│   ├── lip_sync.py
│   ├── advanced_lip_sync.py
│   └── head_pose_estimator.py
├── filter/               # Signal filtering utilities
│   └── kalman_filter.py
├── models/               # Pre-trained models
│   └── Wav2Lip-SD-NOGAN.pt
├── utils/                # Helper functions and shared variables
└── README.md             # Project documentation
```

---

## Contributing

We **welcome contributions!** Follow these steps:

1️⃣ **Fork the Repository**  
🔗 [Fork this Repo](https://github.com/RohanRajesh55/Animotion)

2️⃣ **Clone Your Fork**

```bash
git clone https://github.com/RohanRajesh55/Animotion.git
cd Animotion
```

3️⃣ **Create a Feature Branch**

```bash
git checkout -b feature/your-feature-name
```

4️⃣ **Commit Your Changes**

```bash
git commit -am "Add a new feature"
```

5️⃣ **Push to Your Fork**

```bash
git push origin feature/your-feature-name
```

6️⃣ **Open a Pull Request**  
Submit a **pull request** from your **feature branch** to the **main** repository.

---

## License

This project is **open-source** under the **MIT License**.

---

## Acknowledgments

💡 **MediaPipe** – Real-time face mesh models  
📷 **OpenCV** – Computer vision processing  
🎭 **VTube Studio** – Live 2D avatar animation  
🔬 **Wav2Lip** – High-quality lip sync

Thanks to the **community** and **contributors** for their support! 🚀

---

## Contact

For questions or support, **open an issue** on the [GitHub repository](https://github.com/RohanRajesh55/Animotion).

---
