---

# Face-Recognition-Attendance-System---with-Blink-Detection
The facial recognition attendance system is designed to modernize and secure the attendance tracking  process in educational institutions. It addresses the limitations of traditional methods by automating the  process, reducing human error, and preventing fraudulent attendance. 

## 🌟 Key Features

* **Real-time Face Recognition:** Identifies students using pre-encoded facial signatures.
* **Blink Detection (Liveness Check):** Uses the **Eye Aspect Ratio (EAR)** and 68 facial landmarks to verify the person is real and not a photograph.
* **Automatic Email Notifications:** Sends a free, automated email to the student (via SMTP) confirming their attendance time and status (On-Time/Late).
* **Performance Optimized:** Employs background threading and **Pickle serialization** to ensure the camera feed remains smooth even with large student databases.
* **Dynamic Dashboard:** A modern, dark-themed UI that displays live statistics, attendance rates, and a real-time log.

## 🛠️ Technical Stack

* **Language:** Python 3.x
* **Framework:** Flask (Web Interface)
* **AI Libraries:** * `face_recognition` (Identity matching)
* `dlib` (68-landmark detection)
* `OpenCV` (Video processing)


* **Communication:** `smtplib` (Email delivery)
* **Data Handling:** `Pickle` (Encoding storage) and `Pandas` (Log management)

## 📦 Installation

### 1. Prerequisites

Ensure you have the facial landmark predictor file:

* Download `shape_predictor_68_face_landmarks.dat` and place it in the project root.

### 2. Install Dependencies

```bash
pip install flask opencv-python dlib face_recognition pandas imutils scipy

```

### 3. Setup Known Faces

Create a folder named `known_faces`. Inside, create a subfolder for each student and add their photo:

```text
/known_faces
  /John_Doe
    john.jpg
  /Jane_Smith
    jane.jpg

```

## 📧 Email Configuration

To enable email alerts, update the following variables in `app.py`:

* `SENDER_EMAIL`: Your Gmail address.
* `SENDER_PASSWORD`: Your 16-character **Google App Password**.
* `STUDENT_EMAIL_BOOK`: A dictionary mapping student names to their email addresses.

## 🚀 Usage

1. Run the application:
```bash
python app.py

```


2. Open your browser to `http://127.0.0.1:5000`.
3. Click **"Start Face Recognition"**.
4. Position your face in the camera view and **blink** to record attendance.

## 🛡️ Security Logic

The system uses the **Eye Aspect Ratio (EAR)** formula:



Attendance is only marked if the EAR falls below a threshold (approx. 0.22) for several consecutive frames, confirming a physical blink.

---
