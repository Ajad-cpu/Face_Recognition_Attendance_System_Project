# Face Recognition Attendance System

A **Face Recognition Attendance System** automates attendance by detecting and recognizing faces in real time via webcam. Built in Python with OpenCV and the `face_recognition` library, it captures video, matches faces against a library of reference images, and logs attendance in a CSV file.

---

## 🔍 Key Features

* **Real-Time Detection & Recognition**: Leverages OpenCV and `face_recognition` for live face identification.
* **Modular Scripts**:

  * `main.py`: Main loop—loads encodings, processes webcam feed, annotates faces, logs attendance.
  * `AttendanceProject.py`: Demo comparing two static images with bounding-box visualization.
* **Automated CSV Logging**: Records `Name`, `Time`, and `Date` in `Attendance.csv`, auto-creating the file and headers if missing.
* **Configurable Image Library**: Place reference photos in `Images_Attendance/` with filenames matching person names.

---

## 📁 Project Structure

```plaintext
Face_Recognition_Attendance_System/
├── Images_Attendance/        # Reference images named by person (e.g., John_Doe.jpg)
├── Attendance.csv            # Auto-generated attendance log
├── main.py                   # Live webcam attendance recorder
├── AttendanceProject.py      # Static-image comparison demo
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

---

## 🛠 Prerequisites

* **Python 3.7+**
* **Webcam** connected to your system

**Dependencies** (install via `requirements.txt`):

```text
opencv-python
numpy
face_recognition
pandas
```

```bash
pip install -r requirements.txt
```

---

## 🚀 Installation & Usage

1. **Clone & Navigate**:

   ```bash
   ```

git clone [https://github.com/your-username/Face\_Recognition\_Attendance\_System.git](https://github.com/your-username/Face_Recognition_Attendance_System.git)
cd Face\_Recognition\_Attendance\_System

````
2. **Prepare Reference Images**:
    - Add clear, frontal face images to `Images_Attendance/`.
    - Name each file with the person’s name (e.g., `Jane_Doe.jpg`).
3. **Initialize CSV (Optional)**:
    ```bash
echo "Name,Time,Date" > Attendance.csv
````

4. **Run Live Attendance**:

   ```bash
   ```

python main.py

````
    - A window will display webcam input with detected faces annotated.
    - Logs first detection per session in `Attendance.csv`.
5. **Run Static Demo**:
    ```bash
python AttendanceProject.py
````

```
- Compares two hard-coded images and shows similarity metrics.
```

---

## 🎯 Workflow Overview

1. **Encoding Setup**:

   * Load images from `Images_Attendance/`.
   * Compute face encodings via `face_recognition.face_encodings()`.
2. **Frame Capture**:

   * Read webcam frames at reduced resolution for speed.
   * Convert frames to RGB color space.
3. **Detection & Matching**:

   * Locate faces and compute encodings each frame.
   * Compare against known encodings (`compare_faces` + `face_distance`).
4. **Annotation & Logging**:

   * Draw bounding boxes and names.
   * Append attendance records to `Attendance.csv` with timestamp and date.

---

## ⚙️ Configuration & Best Practices

* **Import Fix**: Ensure `import face_recognition` (no typo).
* **Handle Missing Faces**: Wrap encoding calls in `try/except` to skip images without detectable faces.
* **Performance Tips**:

  * Pre-compute and serialize encodings (e.g., `.npy`) for faster startup.
  * Resize frames or skip frames to improve real-time performance.

---

## 🛣 Future Enhancements

* Web-based dashboard (Streamlit/Flask) for attendance review.
* Database integration (SQL/NoSQL) instead of CSV.
* Liveness detection for anti-spoofing.
* Email notifications for absentees.
* GUI for dynamic face library management.

---

## 📄 License

Distributed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## 🤝 Contributing

Contributions are welcome! Open issues or submit pull requests for improvements.
