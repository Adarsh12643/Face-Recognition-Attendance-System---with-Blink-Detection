# 🎓 Face Attendance with Blink Detection & Email Alerts
  
This project is a professional-grade Biometric Attendance System designed for college environments. 
It utilizes Computer Vision to identify students and verify liveness.

## 🌟 Key Features
  
  * **Real-time Face Recognition:** Identifies students using pre-encoded facial signatures.
  * **Blink Detection (Liveness Check):** Uses the Eye Aspect Ratio (EAR) and 68 facial landmarks to verify the person is real.
  * **Automatic Email Notifications:** Sends an automated email via SMTP confirming attendance status.
  * **Performance Optimized:** Employs background threading and Pickle serialization.
  * **Dynamic Dashboard:** A modern, dark-themed UI displaying live statistics.

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

$$EAR = \frac{||p_2 - p_6|| + ||p_3 - p_5||}{2||p_1 - p_4||}$$

Attendance is only marked if the EAR falls below a threshold (approx. 0.22) for several consecutive frames, confirming a physical blink.
