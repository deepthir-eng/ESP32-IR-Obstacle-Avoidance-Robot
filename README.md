# ESP32-IR-Obstacle-Avoidance-Robot

An embedded robotics project using ESP32 and IR sensors for real-time obstacle detection and autonomous movement, demonstrating sensor interfacing, microcontroller programming, and motor control.

## Introduction

The IoT-Enabled Autonomous Obstacle Detection Robot is an advanced embedded systems project powered by the ESP32 microcontroller and infrared sensors to navigate environments autonomously while transmitting real-time operational data to a cloud dashboard. Built for precision, this project integrates low-level hardware interfacing with IoT connectivity. The onboard ESP32 processes digital signals gathered via IR sensors to execute real-time decision-making, ensuring reliable obstacle detection and avoidance. Simultaneously, telemetry data is published over the internet, allowing remote operators to monitor the robot's status and sensor states live.

## Aim & Objective

**Primary Aim:** To design, develop, and deploy an intelligent, IoT-enabled mobile robot capable of autonomous obstacle detection and remote monitoring using an ESP32 microcontroller and infrared sensors.

**Objective:** Hardware Integration — interface infrared sensors, motor drivers, and DC motors with the ESP32 microcontroller to build a responsive mobile platform.

## Components Used

### 1. ESP32
Acts as the central processing unit and core microcontroller of the robot, providing built-in Wi-Fi and Bluetooth capabilities for executing navigation logic and transmitting IoT telemetry data.

![ESP32](assets/image/Esp32.jpeg)

### 2. L298N Dual H-Bridge Motor Driver
Manages power and directional control for the DC motors, allowing the low-voltage control signals from the ESP32 to safely drive higher-voltage motors.

![L298N Motor Driver](assets/image/H%20bridge%20motor%20driver%20.jpeg)

### 3. DC Motor
Serves as the electromechanical actuators that drive the robot's wheels, converting electrical energy into physical motion for mobility and navigation.

![DC Motor](assets/image/DC%20Motor.jpeg)

### 4. Breadboard
Provides a solderless platform for temporarily connecting and wiring electronic components together during prototyping and circuit assembly.

![Breadboard](assets/image/Bread%20board.jpeg)

### 5. IR Sensor
Acts as the proximity detection unit, emitting and receiving infrared light to instantly detect obstacles in the robot's path and send digital signals to the microcontroller.

![IR Sensor](assets/image/IR%20Sensor.jpeg)

### 6. Programming Cable (USB Cable)
Facilitates serial communication and firmware flashing, allowing you to upload code from your computer directly to the ESP32 microcontroller.

![USB Cable](assets/image/Programing%20cable%20%28%20USB%20Cable%20%29.jpeg)

### 7. Battery Holder
Securely houses the power source and provides organized terminal connections to distribute electrical power safely to the robot's circuitry.

![Battery Holder](assets/image/Battery%20holder%20.jpeg)

### 8. 12V Battery
Delivers the necessary electrical power source to drive the motors, motor driver, and overall hardware system efficiently.

![12V Battery](assets/image/Battery%20.jpeg)

## Circuit Diagram & Connections

![Circuit Diagram](assets/circuit/Circuit%20diagram.jpeg)
![Wiring Connections](assets/circuit/wiring%20connections.jpeg)

## Block Diagram

![Block Diagram](assets/circuit/Block%20diagram.jpeg)

## Working Principle

- **Power Supply:** A 12V battery powers the L298N motor driver, which supplies regulated power to the ESP32 and IR sensors.
- **Proximity Detection:** Infrared sensors continuously scan for obstacles and send digital signals to the ESP32 upon detecting an object.
- **Autonomous Navigation:** The ESP32 processes these sensor signals in real-time and commands the motor driver to steer the DC motors around obstacles.
- **Cloud Telemetry:** Simultaneously, the ESP32 uses its built-in Wi-Fi to transmit live operational status and sensor data to a remote cloud dashboard.

## Code / Software Used

**Platform:** Arduino IDE

```cpp
int IRSensor = 12;

void setup() {
  pinMode(IRSensor, INPUT);
  Serial.begin(115200);
}

void loop() {
  int sensorValue = digitalRead(IRSensor);
}
```

## Step-by-Step Building Process

1. Assemble the chassis, DC motors, wheels, and battery holder.
2. Connect the 12V battery and DC motors to the L298N motor driver.
3. Mount the ESP32 and breadboard, then wire the IR sensors and motor driver to the ESP32 GPIO pins.
4. Upload the firmware using the programming cable and test the obstacle avoidance and Wi-Fi features.

## Problems Faced & Solutions

**Problem 1: IR sensor not detecting obstacles accurately**
Solution: Calibrated the onboard potentiometer on the IR sensor module to set the correct detection range and minimize false triggers.

**Problem 2: Motors not running even after correct code upload**
Solution: Realized the ESP32 GPIO pins alone can't supply enough current to drive the motors directly; routed the motor control signals through the L298N motor driver, powered separately by the battery.

**Problem 3: ESP32 restarting or behaving erratically during motor operation**
Solution: Fixed by ensuring the ESP32 and motor driver shared a common ground and giving the motors a stable, separate power source instead of drawing from the same line as the ESP32.

## Demo & Working Images

**No obstacle detected** — both wheels rotate in the same direction.

![No Obstacle Detected](assets/image/On%20clear%20path.jpeg)

**Obstacle detected** — both wheels rotate in different directions.

![Obstacle Detected](assets/image/Obstacles%20detected%20.jpeg)

📹 [Watch Demo Video](assets/vedio/robo%20vedio.mp4)

## Advantages

- **Autonomous Operation:** Navigates independently using real-time obstacle detection without manual control.
- **IoT Integration:** Leverages the ESP32 for live remote monitoring and cloud telemetry.
- **Cost-Effective:** Built with affordable and accessible electronic components.

## Disadvantages

- **Lighting Interference:** Ambient light and sunlight can cause false obstacle triggers on IR sensors.
- **Surface Limitations:** Struggles to detect dark or non-reflective materials that absorb infrared beams.
- **Range Constraints:** Limited by short-range proximity detection and local Wi-Fi coverage for cloud features.

## Applications

- **Smart Surveillance:** Used for automated patrolling and security monitoring in indoor or restricted environments.
- **Industrial Automation:** Serves as a prototype for Automated Guided Vehicles (AGVs) used in smart warehouses for material handling.
- **Educational & Research Labs:** Acts as a practical learning platform for students to understand embedded systems, microcontroller programming, and IoT.

## Future Scope

- **Advanced Sensor Integration:** Incorporating ultrasonic sensors or LiDAR to improve obstacle detection range and handle varying surface textures.
- **AI and Machine Learning:** Integrating a camera module with edge AI processing on the ESP32 for intelligent computer vision and object classification.
- **Extended Connectivity:** Upgrading cloud telemetry to use cellular IoT (such as 4G/LTE or NB-IoT) to remove local Wi-Fi range limitations.

## Conclusion

This project demonstrates an IoT-enabled autonomous obstacle detection robot built using the ESP32 and IR sensors, capable of real-time obstacle avoidance and remote monitoring via a cloud dashboard. It reinforces core embedded systems and IoT concepts while serving as a foundation for future enhancements like AI-based vision and extended connectivity.

## Acknowledgements

This project was developed during a 3-day workshop on "Wheeled Mobile Robotics," organized by the Department of ECE at ATME College of Engineering, Mysuru, in association with the IETE Student Forum and IIC, held on 22nd, 23rd & 30th September 2026. The session was conducted by Prof. Nagesh M S, Assistant Professor, Dept. of ECE, under the guidance of Dr. Prathibha M K (Convenor) and Ms. Anupama Shettar (ISF Coordinator).

![Workshop Poster](assets/image/woekshop.jpeg)
