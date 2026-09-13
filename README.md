# SpruceBot – Automatic Dust Collecting Robot

## Overview

SpruceBot is an autonomous dust-collecting robot designed to move through an environment while detecting obstacles and responding to the surroundings using multiple sensors.

The system combines an Arduino Mega, ultrasonic sensors, IR sensing, DC geared motors, an L298N motor driver, and a dust-collection mechanism.

## Features

- Autonomous movement
- Obstacle detection
- Obstacle avoidance
- Multi-direction distance sensing
- IR-based detection
- DC motor control
- Dust collection using a fan-based mechanism

## Hardware

| Component | Purpose |
|---|---|
| Arduino Mega | Main controller |
| 3 × HC-SR04 | Left, front and right distance sensing |
| IR Sensor | Detection input |
| L298N | Dual DC motor driver |
| 2 × DC Geared Motors | Robot movement |
| Fan | Dust collection mechanism |
| Power supply/regulator | Power management |
| Robot chassis | Mechanical platform |

## System Architecture

```text
          ┌─────────────────┐
          │   HC-SR04 Left  │
          └────────┬────────┘
                   │
          ┌────────▼────────┐
          │                 │
          │   Arduino Mega  │
          │                 │
          └────┬──────┬─────┘
               │      │
       ┌───────▼─┐  ┌─▼────────┐
       │  L298N  │  │ IR Sensor│
       │ Driver  │  └──────────┘
       └────┬────┘
            │
       ┌────▼─────┐
       │ DC Motors│
       └──────────┘

       HC-SR04 Front
       HC-SR04 Right

              +
              │
              ▼
        Dust Collection
             Fan           
```
             
## Working Principle

The robot uses three ultrasonic sensors positioned to monitor the left, front and right sides.

The Arduino Mega continuously measures the distance detected by the sensors.

A distance threshold of approximately 20 cm is used by the control logic to determine whether an obstacle is present.

Based on the combination of left, front and right distances, the controller changes the motor-control signals through the L298N motor driver.

The IR sensor is also read by the controller and is incorporated into the robot's movement/detection logic.

A fan-based mechanism is used for dust collection.

## Sensor Configuration

### Left Ultrasonic Sensor

- TRIG → Arduino pin 3
- ECHO → Arduino pin 5

### Front Ultrasonic Sensor

- TRIG → Arduino pin 6
- ECHO → Arduino pin 9

### Right Ultrasonic Sensor

- TRIG → Arduino pin 10
- ECHO → Arduino pin 11

### IR Sensor

- IR output → Arduino pin 2

## Motor Control

This allows the robot to:

- Move forward
- Turn left
- Turn right
- Respond to detected obstacles
- React to IR sensor input

## Software

The control program is written in Arduino C/C++.

The program:

1. Triggers each ultrasonic sensor.
2. Measures the echo time.
3. Converts echo time into distance.
4. Reads the IR sensor.
5. Evaluates the sensor conditions.
6. Generates motor-control signals.
7. Changes the robot's movement accordingly.

## My Contribution

My primary contribution to the project was on the hardware and system-integration side.

- Designed and integrated the core hardware circuitry.
- Integrated ultrasonic and IR sensors.
- Interfaced the DC motors with the L298N motor driver.
- Worked on obstacle-detection and movement logic.
- Participated in robot assembly.
- Performed testing and troubleshooting of the system.

## Project Recognition

The project was selected among the Top 100 industry-oriented projects in India.

## Project Images

## Project Images

### Completed Robot

![SpruceBot](images/sprucebot-assembled.jpg)

### Hardware and Electronics

![SpruceBot Hardware](images/sprucebot-chassis.jpg)

### Circuit

![SpruceBot Circuit](hardware/sprucebot-circuit.png)

## Future Improvements

- Improve obstacle-avoidance algorithm.
- Replace blocking delays with non-blocking timing.
- Improve sensor filtering and reliability.
- Improve mechanical dust-collection efficiency.
- Add remote monitoring/control.
- Improve power management and wiring organization.

## Technologies

- Arduino Mega
- Arduino C/C++
- HC-SR04 Ultrasonic Sensors
- IR Sensor
- L298N Motor Driver
- DC Geared Motors
- Embedded Systems
- Robotics

## Author

Sudeep T. Gotur

Electronics and Communication Engineering

