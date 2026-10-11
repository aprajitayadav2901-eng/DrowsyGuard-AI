# DrowsyGuard-AI 🚗👁️

**Real-Time Driver Drowsiness and Yawning Detection System using Python, OpenCV, and MediaPipe**

DrowsyGuard-AI is a computer vision project designed to monitor a driver's facial features through a live webcam feed and identify visual signs associated with drowsiness, such as prolonged eye closure and yawning.

The application uses facial landmarks to calculate the **Eye Aspect Ratio (EAR)** and **Mouth Aspect Ratio (MAR)**. It displays the detection status and counters in a desktop interface built with Tkinter.

## ✨ Features

- **Live webcam monitoring:** Captures video from the system's camera.
- **Facial landmark detection:** Uses MediaPipe Face Mesh to identify important facial points.
- **Eye closure detection:** Calculates EAR to identify potential drowsiness.
- **Yawning detection:** Calculates MAR to identify mouth opening associated with yawning.
- **Real-time status display:** Shows statuses such as Active, Drowsy, and No Face Detected.
- **Detection counters:** Displays eye-closure and yawning counts.
- **Desktop GUI:** Provides Start Live, Stop Live, and Exit controls through Tkinter.
- **Visual feedback:** Highlights relevant facial landmarks and displays detection information on the video feed.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| OpenCV | Webcam capture and image processing |
| MediaPipe Face Mesh | Facial landmark detection |
| NumPy | Numerical calculations and distance measurements |
| Tkinter | Desktop graphical user interface |
| Pillow (PIL) | Displays video frames in the Tkinter interface |

## ⚙️ How It Works

1. The application initializes the webcam and facial landmark detector.
2. The webcam captures live frames when live detection is started.
3. MediaPipe identifies facial landmarks around the eyes and mouth.
4. The program calculates the Eye Aspect Ratio (EAR) and Mouth Aspect Ratio (MAR).
5. These values are compared against configured thresholds.
6. If the eye-closure or yawning conditions are met, the application updates the status and counters.
7. The processed video feed and detection status are displayed in the desktop interface.

### Detection Logic

**1. Eye Aspect Ratio (EAR)**

EAR measures the relative vertical opening of the eye compared with its horizontal width. A lower value can indicate that the eye is closed.

**2. Mouth Aspect Ratio (MAR)**

MAR measures the relative opening of the mouth. A higher value can indicate yawning.

The project uses configurable thresholds and consecutive-frame logic to determine when to display a drowsiness-related status.

## 📁 Project Structure

```text
DrowsyGuard-AI/
├── driver_drowsiness_detection.py
├── requirements.txt
├── .gitignore
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Python installed on your system
- A working webcam
- Git (optional, for cloning the repository)

### 1. Clone the Repository

```bash
git clone https://github.com/aprajitayadav2901-eng/DrowsyGuard-AI.git
```

### 2. Navigate to the Project Folder

```bash
cd DrowsyGuard-AI
```

### 3. Create a Virtual Environment (Recommended)

On Windows:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, you can use the environment's Python executable directly instead.

### 4. Install Dependencies

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

**Compatibility note:** This project uses the legacy `mp.solutions.face_mesh` API. If your installed MediaPipe version does not provide that API, try a compatible version:

```bash
python -m pip install mediapipe==0.10.21
```

If necessary, update `requirements.txt` to pin the compatible version so that the setup is reproducible.

### 5. Run the Application

```bash
python driver_drowsiness_detection.py
```

Allow camera access if prompted. Click **Start Live** to begin detection and **Stop Live** to pause it. Use **Exit** to close the application.

## 🧪 Configuration

The current detection thresholds are defined in `driver_drowsiness_detection.py`:

```python
EAR_THRESHOLD = 0.2
MAR_THRESHOLD = 0.4
CONSEC_FRAMES = 5
```

These values control the eye-closure threshold, mouth-opening threshold, and consecutive-frame condition. They may need adjustment based on camera placement, lighting, and individual facial characteristics.

## 🎯 Applications

- Educational computer vision projects
- Demonstrations of facial landmark detection
- Driver safety monitoring prototypes
- Experiments with eye and mouth movement analysis

## ⚠️ Limitations and Safety

- Detection quality depends on lighting, camera position, and facial visibility.
- Glasses, occlusions, head movement, and individual differences may affect results.
- The current implementation uses threshold-based visual cues and should not be treated as a validated measure of driver fatigue.
- This project is a prototype, not a certified automotive safety system. It should not replace proper rest, safe driving practices, or validated safety equipment.

## 🔮 Future Improvements

- Add an audible alert when drowsiness is detected.
- Improve detection stability with time-based filtering.
- Evaluate the system using a labeled dataset and report measured performance.
- Add configurable thresholds and calibration.
- Improve handling of camera failures and temporary face loss.
- Package the application for easier installation.

## 👩‍💻 Author

**Aprajita Yadav**

- GitHub: [@aprajitayadav2901-eng](https://github.com/aprajitayadav2901-eng)
- Project Repository: [DrowsyGuard-AI](https://github.com/aprajitayadav2901-eng/DrowsyGuard-AI)

