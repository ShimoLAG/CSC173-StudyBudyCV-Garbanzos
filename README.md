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
 The Challenge As a student interested in computer science and game development, I often find myself caught in a cycle of procrastination. Despite knowing how to study, the urge to check my phone or tab out to social media is a constant battle. Standard Pomodoro timers feel "dead" they count down, but they don't care if I get distracted. I need a system that doesn't just track time, but actively keeps me accountable.

The Solution I am building this project to solve my own need for an "accountability partner" that is always watching. By combining my interest in coding (Python/Godot) with my need for focus, I aim to create a "Study Buddy" that makes the abstract concept of discipline tangible. If I pick up my phone, I want immediate feedback (the chicken panicking). If I finish a study session, I want a reward that feels earned (cooking minigames). This project is my attempt to hack my own dopamine system to make studying as addictive as the distractions I am trying to avoid.

**Objectives**
1. To automate my self-discipline: I want to use YOLOv8 object detection to catch myself reaching for my phone before I even realize I'm doing it, creating an external layer of accountability.
2. To make my breaks physically active: Instead of "doom scrolling" during my 5-minute breaks, I want to use MediaPipe hand tracking to play gesture-based minigames (like cooking), which will help me reset my brain and keep my blood flowing.
3. To visualize my productivity: I want to see my study hours turn into something concrete a growing chicken and a collection of eggs so that I feel a sense of progression even when the coursework is difficult.
4. To create a "frictionless" interface: I want to interact with the app using only hand gestures (pinching/dragging) so that I don't have to touch my mouse or keyboard, keeping my hands free for writing or reading notes.


