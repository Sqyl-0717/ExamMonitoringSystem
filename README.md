# ExamMonitoringSystem

An **Intelligent Exam Monitoring System** integrating a PySide6-based GUI, SQLite-backed user authentication, and modular deep-learning pipelines powered by YOLOv5~v8. It supports multiple input sources (camera, video, images, batch files) and provides real-time visualization, cheat-event tracking, and interactive controls.

---

## 🚀 Features

### 🔍 Multi-Model Cheat Detection
- Supports **YOLOv8** (anchor-free, high-accuracy)
- **YOLOv7** (speed–accuracy trade-off)
- **YOLOv6** (industrial-scale deployment)
- **YOLOv5** (PyTorch-based flexibility)

### 🔐 User Authentication & Management
- Login, registration, password reset
- Avatar upload, logout
- PySide6 GUI + SQLite database

### 🎛️ Interactive GUI Controls
- Start/stop video streams
- Save snapshots
- Event filter dropdowns
- Access to help/documentation

### 📺 Real-Time Visual Feedback
- Bounding boxes, class labels, confidence
- Statistics display (e.g., cheat event count)

### 🧪 Training & Evaluation Pipelines
- Train models (`run_train_model.py`)
- Camera test (`run_test_camera.py`)
- Image/video inference (`run_test_image.py`, `run_test_video.py`)
- Headless test mode (`run_main_noLogin.py`)

---

## 📁 Project Structure

```
ExamMonitoringSystem/
├── datasets/             # Annotated data for model training
├── icons/                # Application icons & logos
├── runs/                 # YOLO training outputs
├── test_media/           # Sample test images/videos
├── themes/               # Qt themes & stylesheets
├── ultralytics/          # YOLO integration
├── weights/              # Pre-trained model weights
├── LoginForm.ui          # Qt Designer login form
├── LoginForm.py          # Python wrapper for login UI
├── Recognition_UI.ui     # Qt Designer detection dashboard
├── Recognition_UI.py     # Python wrapper for detection UI
├── RecSystem.qrc         # Qt resource file
├── RecSystem.py          # GUI main application logic
├── run_main_login.py     # Authenticated launcher
├── run_main_noLogin.py   # Bypass login, quick testing
├── run_test_camera.py    # Live camera inference
├── run_test_image.py     # Inference on single image
├── run_test_video.py     # Inference on video files
├── run_train_model.py    # Training orchestration
├── System_login.py       # Login validation backend
└── System_noLogin.py     # Unauthenticated backend logic
```

---

## 📦 Requirements

- Python 3.8+
- `PySide6`
- `ultralytics` (YOLOv5/6/7/8 support)
- `OpenCV-Python`
- `SQLite3` (built-in with Python)

---

## 🛠️ Installation

```bash
# 1. Clone the repository
git clone https://github.com/Sqyl-0717/ExamMonitoringSystem.git
cd ExamMonitoringSystem

# 2. Create and activate virtual environment
python -m venv venv
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt
```

---

## 🧪 Usage

```bash
# 1. Run with Login
python run_main_login.py

# 2. Run without Login
python run_main_noLogin.py

# 3. Test with Camera
python run_test_camera.py

# 4. Test with Image or Video
python run_test_image.py --source path/to/image.jpg
python run_test_video.py --source path/to/video.mp4

# 5. Train a Model
python run_train_model.py --cfg yolov8n.yaml --data data.yaml
```

---

## 📌 Future Work

- Integration of additional pre-trained models (YOLO-NAS, ViT-based detectors)
- Behavior analysis using pose estimation and gaze tracking
- Web-based remote dashboard with live streams
- Email/SMS-based cheat alert automation

---

## 📬 Contact

For questions or contributions, please feel free to submit a [Pull Request](https://github.com/Sqyl-0717/ExamMonitoringSystem/pulls) or open an [Issue](https://github.com/Sqyl-0717/ExamMonitoringSystem/issues).
