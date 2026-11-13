# 🐦 Flappy Bird — Hand Gesture Controlled (C++ & OpenCV)

A classic Flappy Bird clone built from scratch in **C++** using **OpenCV**, where the player controls the bird's flight in real time through webcam hand gesture recognition instead of keyboard inputs.

![Demo](docs/demo.gif)
*(Tip: Record a short clip playing the game via webcam, convert it to `demo.gif`, and place it in a `docs/` folder)*

---

## ✨ Features

- **Real-Time Computer Vision:** Captures webcam feed and processes frames on the fly to detect hand movements/gestures.
- **Custom Game Loop & Physics:** Gravity simulation, jump impulse triggered by gesture detection, dynamic pipe generation, and collision detection rendered directly via OpenCV matrices (`cv::Mat`).
- **Low-Latency Performance:** Written in native C++ for fast frame processing and responsive controls.

---

## 🛠️ Tech Stack

- **Language:** C++ (C++17)
- **Computer Vision & Rendering:** OpenCV (`opencv2`)
- **Build System:** g++ / CMake

---

## 🚀 How to Run

### Prerequisites
Make sure you have a C++ compiler (`g++`) and **OpenCV** installed on your system.

**On Arch / CachyOS:**
```bash
sudo pacman -S opencv gcc pkgconf
```

**On Ubuntu / Debian:**
```bash
sudo apt update && sudo apt install libopencv-dev g++ pkg-config
```

### Build & Execute

1. Clone the repository:
   ```bash
   git clone [https://github.com/HabnergabrielCB/Game_opencv.git](https://github.com/HabnergabrielCB/Game_opencv.git)
   cd Game_opencv
   ```

2. Compile the source code (replace `main.cpp` with your main file name if different):
   ```bash
   g++ main.cpp -o flappy_cv $(pkg-config --cflags --libs opencv4)
   ```

3. Run the game (ensure your webcam is connected):
   ```bash
   ./flappy_cv
   ```

---

## 🧠 How It Works

1. **Frame Capture:** Reads video frames from the default camera (`cv::VideoCapture`).
2. **Gesture Detection:** Isolates the region of interest / skin color thresholding or contour analysis to detect hand elevation/movement.
3. **State Update & Render:** Maps the detected gesture to a vertical velocity impulse, updates obstacle positions, checks bounding-box collisions, and composites the game UI onto the output window.
