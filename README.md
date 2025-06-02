# Autonomous Sock Pickup Vehicle

An AI-powered autonomous robot that navigates indoor environments to detect and pick up socks using real-time object detection and a robotic arm. Built with Raspberry Pi, Arduino, and YOLOv5.

---

## What It Does

This robot:
- Navigates autonomously on a 4-wheel mobile platform
- Detects socks on the floor using a Raspberry Pi camera + YOLOv5
- Picks up detected socks using an Arduino-controlled robotic arm
- Avoids obstacles using ultrasonic sensors

---

## Tech Stack

| Component        | Technology Used                  |
|----------------- |----------------------------------|
| Detection        | YOLOv5 (custom-trained on socks) |
| Onboard Brain    | Raspberry Pi 4B                  |
| Control Logic    | Arduino Uno (servos + motors)    |
| Vision           | OpenCV + Pi Camera               |
| Communication    | UART Serial (PySerial)           |
| Motion/Navigation| DC motors + L298N + Ultrasonic   |
| Training         | Roboflow + PyTorch               |

---

## Project Structure

autonomous-sock-pickup-robot/
├── yolov5/                     # YOLOv5 repo (cloned for training and inference)
├── trained_model/
│   └── best.pt                 # Trained sock detection model
├── scripts/
│   ├── detect_sock.py          # YOLOv5 detection script with camera and Arduino trigger
│   ├── sock_scan_loop.py       # Autonomous movement + object detection loop
│   └── capture_image.py        # Utility script for capturing training images
├── arduino/
│   └── sock_picker.ino         # Arduino code to control servo arm for sock pickup
├── socks_dataset/
│   ├── train/                  # Training images
│   ├── valid/                  # Validation images
│   └── data.yaml               # YOLOv5 dataset config
├── images/
│   └── detected_example.jpg    # Sample detection result
├── videos/
│   └── demo.mp4                # Project demo video
├── requirements.txt
└── README.md

