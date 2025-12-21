# CSC173-StudyBudyCV-Garbanzos

CSC173 Intelligent Systems Final Project
Mindanao State University - Iligan Institute of Technology
Student: Louise Antondy Garbanzos, 2020-1489
Semester: AY 2025-2026 Sem 1

# Abstract

This project presents a desktop-based Augmented Reality (AR) application designed to mitigate student procrastination and improve focus through gamified study companions. Utilizing OpenCV and MediaPipe, the system creates an interactive virtual environment where users care for a digital pet chicken using natural hand gestures (e.g., pinching to feed or pet) rather than traditional input devices. To ensure study adherence, a YOLOv8 object detection model runs in real-time to monitor the workspace for distractions, specifically penalizing smartphone usage during focused sessions.

The application integrates the Pomodoro technique, linking academic discipline to in-game progression. Successful study intervals are rewarded with resource generation, while break periods are transformed into gesture-based AR minigames. These interactive breaks utilize computer vision to translate physical hand movements into gameplay mechanics, encouraging users to engage in brief physical activity before returning to work. By combining behavioral reinforcement with lightweight computer vision, this system demonstrates a novel, unobtrusive approach to digital wellbeing and habit formation.

Keywords: Augmented Reality, Computer Vision, Gamification, Human-Computer Interaction, Productivity, YOLOv8.

# Introduction

 **Problem Statement**
 
 As a student interested in game development, I often find myself caught in a cycle of procrastination. Standard Pomodoro timers feel "dead" to me, they count down, but they don't care if I check my phone. I needed an accountability partner that is always watching.

This project is my attempt to "hack" my own dopamine system. I built a virtual chicken that panics when it sees my phone (using YOLOv8) and demands physical "cooking" minigames (using MediaPipe) during breaks. It turns the discipline of studying into a game I actually want to play.

Formally, this is a desktop application combining Augmented Reality (AR) and Computer Vision. It addresses sedentary study habits and digital distraction by:

1. Active Monitoring: Real-time smartphone detection using YOLOv8.
2. Touchless Interface: Gesture-based interaction using MediaPipe.
3. Gamification: A resource-management loop built in Pygame to incentivize focus.

**Objectives**
1. To automate my self-discipline: I want to use YOLOv8 object detection to catch myself reaching for my phone before I even realize I'm doing it, creating an external layer of accountability.
2. To make my breaks physically active: Instead of "doom scrolling" during my 5-minute breaks, I want to use MediaPipe hand tracking to play gesture-based minigames (like cooking), which will help me reset my brain and keep my blood flowing.
3. To visualize my productivity: I want to see my study hours turn into something concrete a growing chicken and a collection of eggs so that I feel a sense of progression even when the coursework is difficult.
4. To create a "frictionless" interface: I want to interact with the app using only hand gestures (pinching/dragging) so that I don't have to touch my mouse or keyboard, keeping my hands free for writing or reading notes.

# Related Work

1. Forest: Stay Focused, Be Present https://www.forestapp.cc/
2. Habitica: Gamify Your Life https://habitica.com/
3. Student Distraction Detection Using Computer Vision and Machine Learning (2020/2024) https://www.researchgate.net/publication/349645367
4. Focus Plant: Focus Timer & Game https://shikudo.com/focus-plant

# Methodology

**Dataset**

1. Source: Microsoft COCO (Common Objects in Context) Dataset
2. Classes: 80 classes (including "Cell Phone")
3. Size: 330,000 images (Pre-trained by Ultralytics)
4. Preprocessing: Standard YOLOv8 pre-processing (Auto-scaling, normalization)

**Architecture**
Model: YOLOv8n (Nano)
Weights: yolov8n.pt
Inference Size: 640x640 pixels

**Performance (Standard Benchmarks)**
mAP@50 (Mean Average Precision): 52.5% (approx for Nano model on COCO)
Speed: ~80 FPS on CPU (Real-time)

# Installations

1. Clone repo: git clone https://github.com/shimoLAG/CSC173-StudyBudyCV-Garbanzos
2. Install deps: pip install -r requirements.txt
3. Download weights: The YOLOv8n model (yolov8n.pt) will download automatically on the first run.
4. Video Link: https://drive.google.com/file/d/1JFA-y38DIBsmFoTOmTxSUt05yuS8C3nv/view?usp=sharing

requirements.txt: 
pygame>=2.5.0
opencv-python>=4.8.0
mediapipe>=0.10.0
ultralytics>=8.0.0
numpy
