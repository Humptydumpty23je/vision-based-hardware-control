# Real-Time Color Tracking & Hardware Control

This project bridges computer vision and embedded hardware. It uses a Python script running OpenCV to process a live webcam feed, isolate a specific color spectrum (Red) using HSV thresholding, and trigger a physical hardware response via an Arduino microcontroller over a serial connection.

## System Architecture & Hardware Setup

![Hardware Setup] 
<img width="1920" height="1001" alt="sketch_jun24a _ Arduino IDE 2 3 8 26_06_2026 9_44_49 am" src="https://github.com/user-attachments/assets/fb0a31a1-9d03-4484-835c-40532fceb5b7" />



The system consists of two main components:
1. **Vision Processing (Python):** Captures video, masks the designated color, and calculates the pixel density of the target.
2. **Hardware Control (Arduino):** Listens for serial commands from the Python script and actuates a connected load.

### Technical Stack
* **Software:** Python 3.x, OpenCV (`cv2`), NumPy, PySerial
* **Hardware:** Arduino UNO (or compatible microcontroller), Web Camera, 5V Relay/LED

## Demonstration: How It Sees The World

![Computer Vision Feed]()
<img width="1920" height="1030" alt="PythonProject – new_color_tracker py 26_06_2026 9_47_04 am" src="https://github.com/user-attachments/assets/c182b00b-6c79-4da8-b8fa-ce85d0baf2d3" />
<img width="1920" height="1030" alt="PythonProject – new_color_tracker py 26_06_2026 9_47_32 am" src="https://github.com/user-attachments/assets/81ad531e-499b-4c83-a5df-15f2ae9a032b" />

* **HSV Color Space:** The script converts the BGR video feed into HSV (Hue, Saturation, Value). This isolates the color data from lighting intensity, making the tracking highly robust in changing room light.
* **Image Masking:** `cv2.inRange()` creates a binary mask to filter out everything except the target red spectrum.
* **Thresholding:** `cv2.countNonZero(mask)` counts the active pixels. If the count exceeds 5,000, it ensures the object is actually present and not just background noise.
* **Serial Communication:** A control byte (`b'1'` or `b'0'`) is transmitted over UART to the Arduino to establish a fast, low-latency control loop.

## Prerequisites & Installation

### 1. Python Dependencies
Ensure you have Python installed, then install the required libraries:

```bash
pip install opencv-python pyserial numpy<img width="1920" height="1001" alt="sketch_jun24a _ Arduino IDE 2 3 8 26_06_2026 9_44_49 am" src="https://github.com/user-attachments/assets/6d851a0a-e96f-42f9-a237-b7c6cc39565e" />
