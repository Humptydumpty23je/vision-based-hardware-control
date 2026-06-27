# Real-Time Color Tracking & Hardware Control

This project bridges computer vision and embedded hardware. It uses a Python script running OpenCV to process a live webcam feed, isolate a specific color spectrum (Red) using HSV thresholding, and trigger a physical hardware response via an Arduino microcontroller over a serial connection.

## ⚙️ System Overview

The system consists of two main components:
1. **Vision Processing (Python):** Captures video, masks the designated color, and calculates the pixel density of the target.
2. **Hardware Control (Arduino):** Listens for serial commands from the Python script and actuates a connected load (e.g., an LED or a relay module for a lamp).

### Technical Stack
* **Software:** Python 3.x, OpenCV (`cv2`), NumPy, PySerial
* **Hardware:** Arduino UNO (or compatible microcontroller), Web Camera

## 🔧 Prerequisites & Installation

### 1. Python Dependencies
Ensure you have Python installed, then install the required libraries:
```bash
pip install opencv-python pyserial numpy<img width="1920" height="1001" alt="sketch_jun24a _ Arduino IDE 2 3 8 26_06_2026 9_44_49 am" src="https://github.com/user-attachments/assets/9b12754f-5bd1-45fc-9a0b-58413df3566e" />
<img width="1920" height="1030" alt="PythonProject – new_color_tracker py 26_06_2026 9_47_32 am" src="https://github.com/user-attachments/assets/1b3954d1-26dd-459c-95aa-24196413961c" />
<img width="1920" height="1030" alt="PythonProject – new_color_tracker py 26_06_2026 9_47_04 am" src="https://github.com/user-attachments/assets/e3ab3fb1-f401-413a-a0bd-fc88ec327c84" />
