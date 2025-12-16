# Project Development Progress - Louise Antondy Garbanzos

## 1. Model Selection & Architecture
- **Model:** YOLOv8 Nano (`yolov8n`)
- **Weights File:** `yolov8n.pt` (COCO Pre-trained)
- **Framework:** PyTorch via Ultralytics
- **Justification:** Selected the Nano architecture for its lightweight footprint and high inference speed (~80 FPS on CPU), which is critical for maintaining real-time performance when running concurrently with MediaPipe.

## 2. Initial Results (Inference Tests)
- **Object Detection:**
    - Successfully integrated `yolov8n.pt` to detect Class ID 67 (`cell phone`) and Class ID 65 (`remote`).
    - **Confidence Score:** Consistently averages **> 0.80** in standard room lighting.
    - **Latency:** Optimized performance by running inference every 30 frames (0.5s), achieving stable gameplay without lag.
- **Gesture Tracking:**
    - MediaPipe Hands successfully tracks 21 landmarks in real-time.
    - "Pinch" gesture (Index-Thumb distance < 0.05) reliably triggers interaction events.

## 3. Development Milestones
- [x] **Environment Setup:** Configured Python environment with `pygame`, `ultralytics`, and `mediapipe`.
- [x] **Game Engine:** Built the core Pygame loop with AR camera background overlay.
- [x] **Distraction Logic:** Implemented "Panic Mode" penalty when phone/remote is detected.
- [x] **Interaction System:** Created touchless drag-and-drop mechanics for the Chicken, Hay, and Eggs.
- [x] **Game States:** Implemented state machine switching between `STUDY` mode (Timer) and `COOKING` mode (Minigame).

## 4. Current Challenges & Next Steps
- **Challenge:** Occasional false positives where dark rectangular objects (calculators) are detected as phones.
    - *Plan:* Implement a "persistence check" (must be detected for 1 second) to filter glitches.
- **Next Step:** Polish the "Cooking" minigame gesture recognition (Chopping/Stirring) for the final demo.
