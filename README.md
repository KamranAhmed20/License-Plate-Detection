# License Plate Recognition (LPR) and Verification System using YOLOv8 and EasyOCR

---
#### An end-to-end AI-based system for automatic vehicle license plate detection, recognition, and verification from video feeds. This project combines the power of **YOLOv8**, **EasyOCR**, and **OpenCV** to offer a scalable solution for intelligent traffic monitoring and smart law enforcement systems.
---

##  How to Setup

- Upload everything to Google Drive
- Open file1.py through Google Colab (The cells will show the current output, if you want to check it with your video, then follow step 03)
- Change the paths in the file according to your own drive (Sample.mp4, Dataset Paths, CSV Paths, etc)
- just run all the cells.
- Enjoy :)

##  Motivation

As urban areas face increasing vehicle traffic, there's a rising need for **automated, intelligent traffic systems**. While many LPR systems focus on detection or text recognition alone, our work bridges this gap with an **integrated verification mechanism** — simulating real-world applications such as:
- Identifying unregistered vehicles (number plate valid or not)
- Verifying ownership (owner's license information against that registered vehicle)
- Suppose a traffic camera can instantly detect a stolen flagged vehicle and inform the traffic authorities accross different cities.

---

##  Project Workflow

### Step-by-Step Pipeline:
See the complete workflow attached after these steps for detailed understanding.

1. **Video Frame Extraction**  
   - Video input is split into individual frames using OpenCV.
   - Ensures frame-by-frame analysis in real-time simulation.

2. **Vehicle Detection using YOLOv8**  
   - A pre-trained YOLOv8 nano model (`yolov8n.pt`) detects cars in frames.

3. **License Plate Detection**  
   - Another pre-trained model (`license_plate_detector.pt`) is used to extract plates from detected vehicles.

4. **Text Extraction using EasyOCR**  
   - Extracted license plates are cropped and passed through EasyOCR to retrieve alphanumeric data.

5. **Database Matching for Verification**  
   - Extracted plate numbers are normalized and checked against a custom database (containing mock data like owner name, registration status, etc.)
   - Simulates use cases like real-time verification through official government APIs (e.g., NADRA, ETO).
  
   ### Complete Workflow:
<p align="center">
  <img src="https://github.com/user-attachments/assets/fd231210-5fdf-44c4-a231-b10f1e77942d" width="1000" alt="Annotated Frame">
  <br> 
    <em>Figure 1: Complete Workflow </em>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/e7133c38-3c8c-4eb9-886b-b4b717f58b72" alt="Frame before passing to the yolo model i.e before detecting anything" width="48%" />
  &nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/313596f9-c21a-4923-80ab-46f327dbc0c7" alt="esultant Frame after passing through both models" width="48%" />
</p>

<p align="center">
  <em>Figure 2: (Left) Frame before passing to the yolo model i.e before detecting anything  | (Right) Resultant Frame after passing through both models</em>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/2f4938a6-cdcb-4375-8aa3-6cab35ce27fd" width="800" alt="Annotated Frame">
  <br>
  <em>Figure 3: Comparison of different Yolo Models </em>
</p>


---

##  Technologies Used

- **Python** Everything has been done on Google Colab
- **OpenCV** – Video processing and frame extraction  
- **YOLOv8 (Ultralytics)** – Object detection for vehicles  
- **EasyOCR** – Text extraction from license plates  
- **Pandas, NumPy, Matplotlib** – Data processing and visualization

---

##  Key Features

- Real-time processing simulation on video streams
- Modular and scalable pipeline
- Cropped license plate images and annotated frames as output
- End-to-end license plate detection + recognition + verification
- Proof-of-concept for smart traffic and law enforcement applications

---

##  Sample Outputs

- ✅ Annotated video frames with detected vehicles and plates
- ✅ Cropped license plate images saved to `extracted_ocr_plates/`
- ✅ CSV files containing extracted and verified license plate numbers

---

##  Research Contribution (What makes it different from any other LPR)

This project highlights:
- A **complete LPR system**, not just isolated detection or OCR
- Simulated integration with a **vehicle registry database**, here its only demonstrated but could be impactful if implemented with governmental databases, (Same context has been conveyed in our unpublished Research Paper)
- Application in **real-world domains** like smart cities, traffic law enforcement, and stolen vehicle identification

Our **research paper** provides a detailed breakdown of this system’s performance, design choices, and integration potential.

---

##  Future Scope

- Integration with live traffic CCTV feeds
- Connection to real government APIs (e.g., NADRA, Excise Department)
- Inclusion of other detection modules (e.g., helmet detection, seatbelt tracking)

---

## 👥 Authors

- **Hassan Bin Saqib** – [Email](mailto:hassanbinsaqib01@gmail.com)  
- **Awais Khan** – [Email](mailto:awais0swati121@gmail.com)  
- Air University Islamabad

---

## 📜 License

This project is open for educational and research purposes. For commercial use or deployment, proper citations and permissions may be required.

---

## 📎 References

- [YOLOv8 by Ultralytics](https://github.com/ultralytics/ultralytics)
- [EasyOCR](https://github.com/JaidedAI/EasyOCR)
- [Roboflow Plate Detection Model](https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e)
