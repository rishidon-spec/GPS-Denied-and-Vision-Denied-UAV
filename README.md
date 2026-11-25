# GPS-Denied-and-Vision-Denied-UAV
An autonomous drone platform built to navigate, map, and avoid obstacles without GPS satellites or optical cameras.

## Overview
Standard drones lose localization indoors, underground, or in jammed areas where GPS is unavailable, and visual cameras fail in pitch darkness, thick smoke, or heavy dust. This project solves both issues by relying strictly on non-visual, non-satellite sensors fused on an onboard companion computer.

## Sensor Suite (No GPS, No Cameras)
* **Tactical MEMS IMU & Barometer:** Short-term inertial dead reckoning and altitude hold.
* **77 GHz mmWave FMCW Radar:** Doppler velocity estimation and obstacle detection through smoke, dust, and darkness.
* **Solid-State Range-Only LiDAR:** Time-of-flight distance profiling for 3D occupancy mapping without optical imaging.
* **Downward Ultrasonic / ToF Rangefinder:** Ground-relative height tracking for stable takeoff, hover, and landing.

## Software Stack
* **Flight Controller:** PX4 / ArduPilot (custom EKF2 sensor fusion parameters)
* **Middleware:** ROS 2 (Humble / Jazzy)
* **Localization & Mapping:** Extended Kalman Filter (EKF) + Radar-LiDAR Non-Visual SLAM
* **Simulation:** Gazebo dark indoor & tunnel test environments

## Repository Layout
* `docs/` — Project synopsis, wiring schematics, and sensor calibration notes
* `firmware/` — Flight controller parameter files
* `ros2_ws/` — Sensor drivers, EKF fusion nodes, and 3D occupancy grid planner
* `simulation/` — Gazebo world files for testing zero-light, GPS-denied navigation

