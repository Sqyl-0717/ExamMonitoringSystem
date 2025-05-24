# Exam Monitoring System

The Intelligent Exam Monitoring System integrates a PySide6-based GUI with SQLite-backed user authentication and modular deep-learning detection pipelines powered by the YOLO family (v8, v7, v6, v5). It supports multiple input sources (camera, video, images, batch files) and real-time visualization of detection boxes, cheat-event counts, and interactive controls for saving results or filtering alerts.

---

## Features

### • Multi-Model Cheat Detection
Supports YOLOv8 for anchor-free, high-accuracy real-time detection, YOLOv7 for enhanced speed–accuracy trade-off, YOLOv6 optimized for industrial-scale deployment, and YOLOv5’s PyTorch-based ease-of-use.

### • User Authentication & Account Management
Login, registration, password reset, avatar customization, and session logout implemented via PySide6 GUI and SQLite database integration.

### • Interactive GUI Controls
Buttons for starting/stopping media streams, saving detection snapshots, accessing help, and dropdown filters for event types.

### • Real-Time Visual Feedback
Bounding boxes, class labels, confidence scores overlaid on video/images, plus statistics like “number of cheat events”.

### • Training & Evaluation Pipelines
Scripts for model training (`run_train_model.py`), camera testing (`run_test_camera.py`), image/video inference (`run_test_image.py`, `run_test_video.py`), and headless runs without login (`run_main_noLogin.py`).

---

## Project Structure

```
ExamMonitoringSystem/
├── datasets/             # Annotated data for model training
├── icons/                # Application icons & logos
├── runs/                 # YOLO training outputs (logs, weights)
├── test_media/           # Sample images & videos for testing
├── test_media2/          # Additional test datasets
├── themes/               # Qt stylesheets & UI themes
├── ultralytics/          # Ultralytics YOLO codebase integration
├── weights/              # Pre-trained model weights
├── LoginForm.ui          # Qt Designer XML for login dialog
├── LoginForm.py          # Python wrapper for login UI
├── LoginWindow.py        # Main login window logic
├── Recognition_UI.ui     # Qt Designer XML for detection dashboard
├── Recognition_UI.py     # Python wrapper for recognition UI
├── RecSystem.qrc         # Qt resource collection (icons, images)
├── RecSystem.py          # Application entrypoint for GUI logic
├── run_main_login.py     # Launcher requiring user authentication
├── run_main_noLogin.py   # Launcher bypassing login for quick tests
├── run_test_camera.py    # Live-camera inference script
├── run_test_image.py     # Single image inference script
├── run_test_video.py     # Video file inference script
├── run_train_model.py    # Model training orchestration
├── System_login.py       # Backend logic for login validation
└── System_noLogin.py     # Backend logic for unauthenticated operations
```

---

## Requirements

- Python 3.8+
- PySide6 for GUI
- ultralytics (YOLOv8, YOLOv7, YOLOv6, YOLOv5) packages
- SQLite3 (built-in) for user data storage
- OpenCV-Python for image/video I/O

---

## Installation

```bash
# 1. Clone the repo:
git clone https://github.com/yourusername/ExamMonitoringSystem.git
cd ExamMonitoringSystem

# 2. Create and activate a virtual environment:
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# 3. Install dependencies:
pip install -r requirements.txt
```

---

## Usage

```bash
# 1. Run with Login
python run_main_login.py

# 2. Run without Login
python run_main_noLogin.py

# 3. Test Camera Input
python run_test_camera.py

# 4. Test Image/Video
python run_test_image.py --source path/to/image.jpg
python run_test_video.py --source path/to/video.mp4

# 5. Train a Model
python run_train_model.py --cfg yolov8n.yaml --data data.yaml
```

---

## Future Work

- Additional Pre-Trained Models (e.g., YOLO-NAS, Transformer-based detectors)
- Enhanced Behavior Analysis with pose estimation or attention tracking
- Web-Based Dashboard for remote monitoring
- Automated Alerts via email/SMS integration
