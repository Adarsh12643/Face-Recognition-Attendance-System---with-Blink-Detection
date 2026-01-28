---

# Face-Recognition-Attendance-System---with-Blink-Detection
The facial recognition attendance system is designed to modernize and secure the attendance tracking  process in educational institutions. It addresses the limitations of traditional methods by automating the  process, reducing human error, and preventing fraudulent attendance. 
This README is designed for your GitHub repository to showcase the **MERN + Python** architecture of your College Attendance System. It highlights the security features and the multi-device accessibility you’ve planned.

## 🚀 Key Features

* **Multi-Device Registration:** Students can enroll from any device by logging in with their unique **College ID and Password**.
* **Liveness Detection:** Integrated **Blink Detection** (Eye Aspect Ratio - EAR) to prevent spoofing using photos or videos.
* **Microservices Architecture:** Uses **React** for the frontend, **Node.js/Express** for the backend gateway, and **Python** for AI processing.
* **Instant Notifications:** Real-time **Email alerts** (and optional SMS) sent to students upon successful attendance marking.
* **Compact Deployment:** Optimized to run on small-form-factor devices like **Raspberry Pi 5** or **NVIDIA Jetson Nano**.
* **Startup Optimization:** Uses **Pickle serialization** to load hundreds of face encodings in milliseconds.

## 🏗️ System Architecture

The project is split into three main components:

1. **Frontend (React):** A responsive dashboard for student registration and admin monitoring.
2. **Backend (Node.js & MongoDB):** Manages student databases, authentication (ID/Password), and serves as a bridge to the AI engine.
3. **AI Service (Python):** Handles the "heavy lifting" using `OpenCV`, `dlib`, and `face_recognition` for biometric verification.

## 🛠️ Hardware Requirements

For a professional college station, we recommend:

* **Compute:** Raspberry Pi 5 (8GB RAM).
* **Camera:** Raspberry Pi Camera Module 3 or 1080p USB Webcam.
* **Display:** 7" DSI Touchscreen for the user interface.
* **Lighting:** Consistent LED ring light for accurate landmark detection.

## 💻 Tech Stack

* **Frontend:** React.js, Tailwind CSS
* **Backend:** Node.js, Express.js
* **Database:** MongoDB (Student Profiles & Logs)
* **AI/ML:** Python, OpenCV, Dlib (68 Facial Landmarks), face_recognition
* **Communication:** Socket.io (Real-time updates), SMTP (Email Notifications)

## 🔧 Installation & Setup

1. **Clone the Repo:**
```bash
git clone https://github.com/yourusername/college-attendance-system.git

```


2. **Setup Python AI Service:**
* Download `shape_predictor_68_face_landmarks.dat`.
* `pip install opencv-python dlib face_recognition flask imutils`
* `python app.py`


3. **Setup Node.js Backend:**
* `cd backend && npm install`
* Configure your `.env` with MongoDB URI and Email credentials.
* `npm start`


4. **Setup React Frontend:**
* `cd frontend && npm install`
* `npm start`



## 🔒 Security

Face data is converted into a **128-dimensional embedding** (vector). The system stores these mathematical signatures rather than raw images to enhance student privacy.

---
