# CSC173 Deep Computer Vision Project Proposal

Student: Louise Antondy Garbanzos, 2020-1489
Date: Dec, 11, 2025

# 1. Project Title
StudyBudyCV

# 2. Problem Statement
In the modern academic landscape, students face significant challenges in maintaining prolonged focus due to the ubiquity of digital distractions. While traditional productivity tools like Pomodoro timers are widely available, they suffer from passive interaction—they track time but lack the capability to enforce discipline or provide immediate consequences for distraction. This creates a "feedback void" where students are not held accountable for their actions in real-time.

This project bridges this gap by developing an AR-based desktop companion that actively monitors the workspace using computer vision. By penalizing smartphone usage (active accountability) and rewarding study intervals with gesture-based minigames (dopamine-driven reinforcement), the system transforms the abstract struggle of self-regulation into a tangible, gamified experience.

# 3. Objectives

1. To develop a touchless, gesture-controlled AR interface using MediaPipe and OpenCV that allows users to interact with a virtual study companion and play physically active minigames during break periods.
2. To integrate YOLOv8 object detection for real-time distraction monitoring, creating an automated accountability system that penalizes smartphone usage and gamifies sustained academic focus.  

# 4. Dataset Plan

Source: MS COCO 2017 (Common Objects in Context) [118k Train / 5k Val images]
https://www.kaggle.com/datasets/sabahesaraki/2017-2017/data

Classes: cell phone (Class ID: 67), remote (Class ID: 65)

Acquisition: Automated download via Ultralytics API (yolov8n.pt) utilizing pre-trained weights from the official COCO benchmark.

# 5. Technical Approach

1. Architecture Sketch: A real-time loop where OpenCV captures webcam frames then YOLOv8 runs inference for distraction detection then MediaPipe extracts hand landmarks for gesture control then Pygame renders the AR overlay and manages game state logic.

2. Model: YOLOv8n (Nano) for object detection; MediaPipe Hands for pose estimation.
   
3. Framework: PyTorch (via Ultralytics) for the backend; OpenCV and Pygame for the frontend application.
   
4. Hardware: Local CPU (optimized for real-time ~30 FPS on standard laptops) or Local GPU (NVIDIA CUDA) if available.

# 6. Expected Challenges & Mitigations

Challenge: False positives (calculators/wallets as phones) Solution: Confidence threshold >0.5 + Temporal consistency check (must detect for >1s).

Challenge: High CPU latency (Running 2 AI models) Solution: Asynchronous processing (Run YOLO every 30 frames; MediaPipe every frame).

Challenge: 2D Depth perception limits Solution: Use "Pinch" gesture (Index-Thumb distance) as a binary interaction trigger.
