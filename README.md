
# Autonomous 4WD Obstacle-Avoiding Rover

This repository contains the source code and hardware documentation for a custom-built, 4-wheel drive (4WD) autonomous robotic vehicle. The rover is engineered to navigate its environment independently by continuously scanning for obstacles and calculating the optimal path in real time.

## Overview

The primary objective of this project was to design and assemble a fully autonomous rover from scratch, combining low-level hardware integration with responsive software algorithms. The project involved manual component soldering, circuit design, and C++ programming for embedded systems.

## Key Features

* **Dynamic Spatial Scanning:** The rover utilizes a servo-mounted ultrasonic sensor that continuously pans left and right. This allows the system to sweep the forward environment, measure distances, and identify the widest free path.
* **Autonomous Navigation Logic:** Powered by a custom real-time algorithm, the vehicle processes sensor data on the fly to avoid obstacles, back up when trapped, and redirect itself towards open spaces without human intervention.
* **Dual-Source Power Management:** The power architecture integrates standard battery packs alongside a rechargeable accumulator. This dual system ensures optimal power distribution between the microcontrollers and the high-draw DC motors, significantly extending operational uptime.
* **Custom Hardware Assembly:** All electronic components, including motor drivers and sensor interfaces, were manually soldered and integrated onto a custom circuit board, ensuring robust physical connections and an optimized hardware layout.

## Hardware Components

* Arduino Microcontroller (Logic & Control)
* 4x DC Gear Motors & Wheels (4WD System)
* Motor Driver Module (e.g., L298N / L293D)
* HC-SR04 Ultrasonic Distance Sensor
* Micro Servo Motor (For sensor panning)
* Custom Circuit Board (Manually soldered)
* Standard Battery Pack & Rechargeable Accumulator

## Software & Technologies

* **Language:** C++
* **Environment:** Arduino IDE
* **Libraries Used:** Standard Servo library (for sensor panning)

## How It Works

1. **Scan:** The ultrasonic sensor looks forward. If the path is clear, the rover moves forward at standard speed.
2. **Detect:** If an obstacle is detected within a predefined threshold, the motors immediately halt.
3. **Evaluate:** The servo motor sweeps the ultrasonic sensor to the left and then to the right, recording the distance in both directions.
4. **Decide:** The microcontroller compares the available distances and pivots the rover towards the direction with the most open space.
5. **Execute:** The rover resumes forward movement in the new, clear direction.
