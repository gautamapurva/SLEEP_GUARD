Sleep Guard: Drowsiness Detection System
Sleep Guard is a real-time computer vision application designed to detect user drowsiness by monitoring eye-closure patterns. Using a webcam, the system tracks facial landmarks to calculate the Eye Aspect Ratio (EAR) and triggers an automated alarm when the eyes remain closed beyond a configured threshold.

Features
Real-Time Analysis: Uses MediaPipe Face Mesh for high-performance landmark detection.

Smart Alert System: Triggers an audio alarm using pygame when drowsiness is detected.

Visual UI: Displays "Awake" vs "Sleeping" status overlays, a progress bar for eye-closure duration, and live EAR telemetry.

Safety Thresholds: Adjustable time and sensitivity settings.

Prerequisites
To run this project, you will need Python installed. You must also install the required libraries:

Bash
pip install opencv-python mediapipe numpy pygame
Setup Instructions
Clone the repository:

Bash
[git clone https://github.com/gautamapurva/SLEEP_GUARD.git](https://github.com/gautamapurva/SLEEP_GUARD.git)
cd sleep-guard
Configure the Alarm:
Update the ALARM_SOUND_FILE variable in main.py to point to your preferred .mp3 or .wav file:

Python
ALARM_SOUND_FILE = r"C:\path\to\your\alarm.mp3"
Adjust Settings (Optional):

EAR_THRESHOLD: Adjust (default 0.22) to tune sensitivity based on your camera and eye shape.

EYE_CLOSED_SECONDS: Set how long the user must have their eyes closed before the alarm triggers (default 2.5s).

Run the Application:

Bash
python main.py
How It Works
The project follows a modular pipeline to ensure efficiency:

OpenCV: Captures raw frames and handles video display.

MediaPipe: Identifies 468 3D face landmarks to isolate eye coordinates.

NumPy: Performs efficient geometric calculations to determine the EAR.

Pygame: Manages non-blocking audio playback to ensure the alarm doesn't freeze the camera feed.

Troubleshooting
Camera Not Opening: Ensure your camera index in main.py (line 120) is set to 0 for the default webcam.

MediaPipe Errors: If you encounter AttributeError, ensure you are using a compatible version of MediaPipe (pip install mediapipe==0.10.21).

Permissions: Ensure your operating system grants Python access to the webcam and microphone.

License
This project is open-source and available for educational purposes.
