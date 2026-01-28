---

# Face-Recognition-Attendance-System---with-Blink-Detection
The facial recognition attendance system is designed to modernize and secure the attendance tracking  process in educational institutions. It addresses the limitations of traditional methods by automating the  process, reducing human error, and preventing fraudulent attendance. 

## 🌟 Key Features

1. Real-time Face Recognition: High-accuracy identity matching using 128-dimensional facial embeddings.
2. Blink Detection (Liveness Check): Utilizes the Eye Aspect Ratio (EAR) and 68 facial landmarks to verify the presence of a real human, preventing spoofing via photos or videos.
3. Automated Email Notifications: Sends free, automated email receipts (via SMTP) confirming attendance time, date, and status (On-Time/Late).
4. Performance Optimized: Employs background threading to maintain a smooth camera feed (30+ FPS) and uses Pickle serialization for near-instant startup.
5. Modern Web Dashboard: A responsive, dark-themed interface showing live statistics, daily attendance rates, and a real-time event log.

##🛠️ Technical Stack

*Backend:* Python 3.x, Flask

*Computer Vision:* OpenCV, dlib (68-point landmarks), face_recognition

*Data Analysis:* Pandas, NumPy

*Communication:* smtplib (Email), SSE (Real-time UI updates)

## 🛡️ The Security Logic (Blink Detection)

To prevent cheating, the system calculates the Eye Aspect Ratio (EAR) for every frame. Attendance is only recorded if a physical blink is detected, confirmed by the EAR falling below a specific threshold (e.g., 0.22) for consecutive frames.

$$EAR = \frac{||p2 - p6|| + ||p3 - p5||}{2||p1 - p4||}$$

This ensures that only a "live" person can mark attendance.

## 📦 Installation & Setup

1. Prerequisites

* Ensure you have the facial landmark predictor file:
Download shape_predictor_68_face_landmarks.dat and place it in the project root.

2. Install Dependencies

pip install flask opencv-python dlib face_recognition pandas imutils scipy


3. Setup Known Faces

Create a folder named known_faces. Organize images into subfolders named after the students:

/known_faces
  /John_Doe
    photo1.jpg
  /Jane_Smith
    photo1.jpg


## 📧 Email Configuration

To enable free email alerts, generate a Google App Password and update the following variables in app.py:

SENDER_EMAIL = "your_college_admin@gmail.com"
SENDER_PASSWORD = "your_16_char_app_password"

# Map student names to their emails
STUDENT_EMAIL_BOOK = {
    "John_Doe": "john.student@college.edu",
    "Jane_Smith": "jane.student@college.edu"
}


## 🚀 Usage

Run the application:

python app.py


Open your browser to http://127.0.0.1:5000.

Click "Start Face Recognition".

Position your face and blink to record your attendance.

## 🗺️ Roadmap

[ ] Student Registration Portal: React-based mobile-friendly enrollment page.
[ ] Node.js Gateway: Scalable backend for multi-classroom deployments.
[ ] Hardware Kiosk: Deployment on Raspberry Pi 5 with a 7" Touchscree

---
