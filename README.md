# Face Recognition Attendance System

A **Face Recognition Attendance System** automates daily attendance logging by detecting and recognizing faces in real time. Built in Python with OpenCV and the `face_recognition` library, this project captures webcam footage, matches faces against a library of known images, and records attendance to a CSV file.

---

## 🔍 Features

* **Real-Time Face Detection & Recognition**: Uses OpenCV and `face_recognition` (dlib-based) to identify faces from live webcam feed.
* **Multiple Script Organization**:

  * `main.py`: Core attendance loop—loads known face encodings, captures video, recognizes faces, logs attendance.
  * `AttendanceProject.py`: Standalone demo comparing two sample images (e.g. Modi vs. test image) and drawing bounding boxes.
* **Attendance Logging**: Appends name, timestamp, and date to `Attendance.csv`, with header auto-initialization if the file doesn’t exist.
* **Configurable Image Library**: Place reference photos in `Images_Attendance/` named by person (e.g. `Alice.jpg`).
* **CSV Output**: Attendance entries stored in `Attendance.csv` for easy import into Excel or database.

---

## 📁 Project Structure

```
Face_Recognition_Attendance_System/
├── Images_Attendance/        # Reference face images (filenames → person names)
│   ├── alice.jpg
│   └── bob.png
├── Attendance.csv            # Generated attendance log
├── main.py                   # Live webcam attendance recorder
├── AttendanceProject.py      # Demo script: compare two static images
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

---

## 🛠 Prerequisites

* **Python 3.7+**
* **Webcam** connected to your system

**Python Packages** (in `requirements.txt`):

```text
opencv-python
numpy
face_recognition
pandas
```

Install them via:

```bash
pip install -r requirements.txt
```

---

## 🚀 Installation & Usage

1. **Clone the repository**:

   ```bash
   ```

git clone [https://github.com/your-username/Face\_Recognition\_Attendance\_System.git](https://github.com/your-username/Face_Recognition_Attendance_System.git)
cd Face\_Recognition\_Attendance\_System

````

2. **Prepare your image library**:
- Add clear, frontal face images to `Images_Attendance/`.
- Name each file using the person’s name (e.g. `John_Doe.jpg`).

3. **Initialize Attendance CSV** (optional):
The script auto-creates `Attendance.csv` with headers if it is missing. To pre-create manually:
```bash
echo "Name,Time,Date" > Attendance.csv
````

4. **Run live attendance**:

   ```bash
   ```

python main.py

````
   - A window will open showing webcam input with recognized faces outlined.
   - Each first-seen face per session is logged to `Attendance.csv`.

5. **Run demo comparison** (static images):
   ```bash
python AttendanceProject.py
````

* Compares two hard-coded images and displays similarity score.

---

## 🎯 How It Works

1. **Load & Encode Known Faces** (`main.py`):

   * Reads all images in `Images_Attendance/`.
   * Computes face encodings via `face_recognition.face_encodings()`.
2. **Capture Video Frames**:

   * Grabs frames from webcam at 25% resolution for speed.
   * Converts to RGB for recognition.
3. **Detect & Recognize**:

   * Locates faces and computes encodings each frame.
   * Compares against known encodings (`compare_faces` + `face_distance`).
4. **Annotate & Log**:

   * Draws bounding boxes and names on video feed.
   * Marks attendance in `Attendance.csv` with timestamp and date.

---

## ⚙️ Configuration & Tips

* **Import Correction**: Ensure all scripts use `import face_recognition` (not `face_recognitions`).
* **Error Handling**:

  * Wrap `face_recognition.face_encodings(img)[0]` in try/except to skip images without detectable faces.
* **Performance**:

  * Pre-compute encodings in a separate `train.py` and serialize to `.npy` for faster startup.
  * Adjust frame resize factor or skip frames for smoother display.

---

## 🛣 Future Improvements

* Add a **web-based dashboard** (Streamlit or Flask) for attendance review.
* Integrate with a **SQL/NoSQL database** in place of CSV.
* Implement **anti-spoofing** checks (liveness detection).
* Add **email alerts** for absent students.
* Build a **GUI** for on-the-fly addition/removal of student faces.

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or submit pull requests to propose enhancements or fixes.
