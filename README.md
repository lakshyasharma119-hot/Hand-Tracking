# Hand-Tracking Air Canvas 🖐️✨

A high-performance, real-time web application that allows users to draw and interact with a digital canvas entirely through natural hand gestures using a standard webcam. 

Built completely client-side using **Vanilla JavaScript**, **HTML5 Canvas**, and **Google MediaPipe**, this app requires zero server overhead and runs instantly in the browser.

## 🌐 Live Demo
Try it directly in your browser without downloading anything:  
👉 **[Launch Live App](https://lakshyasharma119-hot.github.io/Hand-Tracking/)**

## ✨ Key Features

### 1. Robust Gesture Recognition
Most hand-tracking demos use a simple "highest finger" check, which leads to misfires. This app implements a strict 5-finger conditional state machine:
* **DRAW:** Only triggers when the index finger is strictly up AND the thumb, middle, ring, and pinky fingers are folded.
* **MOVE:** Calculates the euclidean distance between the thumb tip and index tip. A distance `< 45px` triggers a canvas translation state, allowing you to "pinch" and drag drawn elements across the screen.

### 2. Custom Render Engines
The Canvas 2D context is pushed to its limits with custom rendering styles and a live particle system:
* **Laser:** A sharp core stroke with a soft, dynamically scaled white highlight.
* **Neon:** Three stacked glow layers utilizing `shadowBlur` and RGBA alpha channels to simulate a real neon tube.
* **Dotted:** Pulsing coordinate points with a tiny spark rendered on each node.
* **Rainbow:** Uses an algorithmic HSL to HEX converter to shift colors dynamically as the path is drawn.
* **Particle Sparks:** A custom physics class (`class Spark`) generates decaying, gravity-affected sparks at the tip of the index finger while drawing.

### 3. Glassmorphism UI & Boot Sequence
* Features a custom, terminal-style boot loading sequence that visualizes the MediaPipe model fetching and camera initialization.
* Fully responsive, mobile-friendly toolbar with dynamic color swatches and thickness sliders.

## 🛠️ Tech Stack
* **Language:** Vanilla JavaScript (ES6+)
* **Frontend UI:** HTML5 & CSS3 (Custom variables, glassmorphism)
* **Rendering:** HTML5 `<canvas>` API
* **AI/Vision:** Google MediaPipe Hands API (`@mediapipe/hands`, `@mediapipe/camera_utils`)

## 🚀 How to Run Locally

Because this project is built with zero dependencies and no build steps, running it locally is incredibly simple:

1. Clone the repository:
   ```bash
   git clone [https://github.com/lakshyasharma119-hot/Hand-Tracking.git](https://github.com/lakshyasharma119-hot/Hand-Tracking.git)
