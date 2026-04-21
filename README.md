# 🌾 Wildlife Intrusion Detection System using YOLOv8 & LoRa

## 🚀 Overview

This project is a real-time wildlife intrusion detection system designed to prevent crop damage in farmlands near forest regions. It combines **computer vision**, **embedded systems**, and **long-range wireless communication** to detect animals and alert farmers instantly.

The system performs edge-based object detection using **YOLOv8**, captures images upon detection, and transmits alerts using a structured communication protocol over **LoRa** (simulated in this implementation).

---

## 🧠 Key Features

* Real-time animal detection using YOLOv8
* Edge-based inference with low latency
* Long-range communication using LoRa (simulated)
* Structured message protocol: `$DATA#`
* Image capture on detection events
* Alert generation system (console / extendable to buzzer/email)

---

## 🏗️ System Architecture

1. Camera captures live video feed
2. YOLOv8 model processes frames and detects objects
3. If an animal is detected:

   * Image is captured
   * Detection metadata is formatted (`$animal#`)
   * Data is transmitted via LoRa (simulated)
4. Receiver system triggers alert

---

## 🛠️ Tech Stack

* **Python** (Core implementation)
* **OpenCV** (Image processing)
* **Ultralytics YOLOv8** (Object detection)
* **PySerial** (Communication layer - simulated)
* **Embedded Systems** (Arduino, LoRa modules - conceptual integration)

---

## 📁 Project Structure

```
wildlife-intrusion-system/
│
├── src/
│   ├── animal_detection.py
│   ├── train_yolo.py
│   └── yolov8.py
│
├── arduino/
│   ├── sender.ino
│   └── receiver.ino
│
├── assets/
│   ├── demo.png
│   ├── transmitter.png
│   └── receiver.png
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```
git clone https://github.com/YOUR_USERNAME/wildlife-intrusion-system.git
cd wildlife-intrusion-system
```

### 2. Create virtual environment (recommended)

```
python -m venv venv
venv\Scripts\activate
```

### 3. Install dependencies

```
python -m pip install -r requirements.txt
```

---

## ▶️ How to Run

```
python src/animal_detection.py
```

* Webcam will open
* Detection will start in real-time
* Console will display alerts like:

```
[ALERT] Detected: person (0.90) → Sent: $person#
```

---

## 🧪 Simulation Mode

Since hardware (Arduino + LoRa) may not always be available, the communication layer is simulated using console outputs.

This allows:

* End-to-end system validation
* Testing of communication protocol
* Demonstration without physical devices


## 📡 Communication Protocol

The system uses a simple structured format for transmission:

```
$<animal_name>#
```

Example:

```
$elephant#
```

This ensures easy parsing and reliability across transmitter and receiver modules.

---

## 🔮 Future Improvements

* Integration with real LoRa hardware modules
* Deployment on Raspberry Pi for edge computing
* Real-time dashboard for monitoring
* 5G-based IoT communication integration
* Improved model trained on wildlife-specific dataset


