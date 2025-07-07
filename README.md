# Face Recognition Attendance System

A simple, real-time **Face Recognition Attendance System** built in Python. This project uses your webcam to detect and recognize faces, then logs attendance automatically into a CSV file with timestamps.

---

## 🚀 Key Features

* **Real‑Time Detection & Recognition**: Leverages [OpenCV](https://opencv.org/) and the [`face_recognition`](https://github.com/ageitgey/face_recognition) library to process live video feed.
* **Automated Attendance Logging**: Records **Name**, **Date**, and **Time** into `Attendance.csv`, creating it with headers if it doesn’t exist.
* **Modular Design**:

  * `main.py`: Runs the live webcam attendance loop.
  * `AttendanceProject.py`: Demo comparing two static images for face matching.
* **Configurable Reference Library**: Add reference images in `Images_Attendance/` named after each person (e.g., `John_Doe.jpg`).

---

## 🗂️ Project Structure

```
Face_Recognition_Attendance_System/
├── Images_Attendance/        # Reference images for each person
│   └── Name.jpg
├── Attendance.csv            # Auto-generated attendance log
├── main.py                   # Live webcam attendance recorder
├── AttendanceProject.py      # Static-image comparison demo
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

---

## ⚙️ Prerequisites

* **Python 3.7+**
* **Webcam** connected to your computer

Install dependencies via pip:

```bash
pip install -r requirements.txt
```

> **requirements.txt** includes:
>
> * opencv-python
> * numpy
> * face\_recognition
> * pandas

---

## 🛠️ Installation & Usage

1. **Clone this repository**:

   ```bash
   ```

git clone [https://github.com/Ajad-cpu/Face\_Recognition\_Attendance\_System\_Project.git](https://github.com/Ajad-cpu/Face_Recognition_Attendance_System_Project.git)
cd Face\_Recognition\_Attendance\_System\_Project

````

2. **Prepare Reference Images**:
- Place clear, frontal face photos in `Images_Attendance/`.
- Filename should match the person’s name (e.g., `Jane_Doe.jpg`).

3. **(Optional) Initialize CSV**:
```bash
echo "Name,Time,Date" > Attendance.csv
````

4. **Run Live Attendance**:

   ```bash
   ```

python main.py

````
- A window will open showing webcam feed with detected faces and names.
- First detection per session is logged to `Attendance.csv`.

5. **Run Static Comparison Demo**:
```bash
python AttendanceProject.py
````

* Compares two hard‑coded images and visualizes face matching.

---

## 🔍 How It Works

1. **Load & Encode Faces**

   * Reads `Images_Attendance/`, computes face encodings via `face_recognition`.
2. **Capture & Preprocess Frames**

   * Grabs webcam frames, resizes and converts to RGB for faster processing.
3. **Detect & Recognize**

   * Finds face locations and encodings each frame.
   * Matches against known encodings using `compare_faces` and `face_distance`.
4. **Annotate & Log**

   * Draws bounding boxes and labels on video.
   * Records attendance once per face per session in `Attendance.csv`.

---

## 💡 Configuration Tips & Best Practices

* **Performance**: Precompute and save encodings (e.g., with `pickle` or `.npy`) to speed up startup.
* **Error Handling**: Wrap encoding calls to skip images without detectable faces.
* **Scalability**: Increase `frame_skip` to process every nth frame if performance lags.

---

## 🔧 Future Enhancements

* **Web Dashboard**: Use Flask/Streamlit to view and manage attendance online.
* **Database Integration**: Store logs in SQL/NoSQL instead of CSV.
* **Liveness Detection**: Prevent spoofing using blink or movement detection.
* **GUI**: Add an interface to add/remove reference images dynamically.

---

## 📄 License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or submit pull requests to improve features, documentation, or performance.

---

## 📬 Contact

For questions or feedback, open an issue or reach out at **[your.email@example.com](mailto:your.email@example.com)** (replace with your contact).
