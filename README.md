# DriveGuard Lab – Overcurrent and Stall Protection of BLDC Motor Drive

A browser-based software simulation demonstrating overcurrent detection and stall protection logic for a Brushless DC (BLDC) motor drive.

## 📌 Project Overview

**DriveGuard Lab** is a software-based demonstration platform designed to explain and visualize basic protection mechanisms used in BLDC motor drives.

The application provides a virtual motor test bench where users can simulate normal motor operation, inject overcurrent and stall conditions, monitor virtual motor parameters, and observe how the protection logic responds to abnormal operating conditions.

The project is developed using **HTML5, CSS3, and JavaScript** and runs directly in a web browser without requiring additional hardware or software installation.

## 🎯 Objectives

- Understand the operating principle of BLDC motor drives.
- Demonstrate overcurrent protection logic.
- Implement time-based stall detection.
- Monitor virtual motor current and rotor speed.
- Demonstrate fault detection, fault latching, and manual reset.
- Develop an interactive and low-cost motor protection learning environment.

## ✨ Features

### 1. Virtual Motor Test Bench
- Normal motor operation simulation.
- Adjustable virtual motor current.
- Adjustable virtual motor speed.
- Configurable overcurrent trip threshold.
- Adjustable stall detection timeout.

### 2. Overcurrent Protection
The application continuously compares the virtual motor current with the configured current threshold.

**Protection condition:**

`Motor Current > Overcurrent Threshold`

When the current exceeds the selected limit, the system:
- Detects an overcurrent condition.
- Activates the fault state.
- Turns the simulated drive output OFF.
- Requires manual fault reset.

### 3. Stall Detection

The application detects a simulated motor stall by monitoring rotor speed.

The implemented protection logic uses:
- Start-up grace period: 2 seconds.
- Low-speed threshold: Below 50 RPM.
- Configurable stall timeout.

If the motor speed remains below the defined threshold for the configured duration after the start-up grace period, a stall fault is triggered.

### 4. Live Telemetry Dashboard

The interface displays:
- Motor current (A).
- Motor speed (RPM).
- Drive output status (ON/OFF).
- Virtual rotor animation.
- Fault status.
- Stall timer.
- Event console and system messages.

### 5. Fault Management

The application supports:
- Fault detection.
- Fault latching.
- Simulated drive shutdown.
- Manual fault reset.
- Event logging.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| HTML5 | Application structure |
| CSS3 | Interface design and animations |
| JavaScript | Protection logic and simulation |
| Web Browser | Application execution |

## ⚙️ How to Run

No installation or external libraries are required.

1. Clone this repository:

   ```bash
   git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
   ```

2. Navigate to the project directory:

   ```bash
   cd YOUR-REPOSITORY
   ```

3. Open the HTML file in a browser:

   ```bash
   xdg-open driveguard_bldc_protection_lab.html
   ```

   Alternatively, double-click the HTML file and open it using Chrome, Brave, or Firefox.

4. Start experimenting with the available controls.

## 🧪 Simulation Test Cases

| Test Case | Input Condition | Expected Result |
|---|---|---|
| Normal Operation | Normal current and speed | Drive RUNNING |
| Overcurrent | Current exceeds trip threshold | Overcurrent fault |
| Motor Stall | Speed remains below 50 RPM | Stall fault after timeout |
| Motor Stop | Stop button selected | Drive OFF |
| Fault Reset | Reset button selected | Fault cleared |

## 🧠 Technical Background

A BLDC motor generates back electromotive force (Back EMF) when its permanent-magnet rotor rotates relative to the stator windings.

The relationship between back EMF and angular speed is approximately:

\[
E_b = K_e\omega
\]

Where:

- \(E_b\) = Back EMF
- \(K_e\) = Back EMF constant
- \(\omega\) = Angular speed

Back EMF plays an important role in motor operation because it opposes the applied voltage and influences winding current.

During a rotor stall, back EMF decreases because rotor speed approaches zero. This can contribute to excessive winding current and motor heating.

**Note:** Back EMF is included as theoretical background in this project. The current software simulation does not directly measure or calculate Back EMF.

## 📂 Project Structure

```text
Overcurrent-and-Stall-Protection/
│
├── driveguard_bldc_protection_lab.html
│
└── README.md
```

## ⚠️ Project Limitations

This is currently a software-only simulation.

- No physical BLDC motor is connected.
- No ESP32 or other microcontroller is used.
- No physical current or speed sensors are connected.
- No actual PWM generation or inverter switching is performed.
- All motor parameters are virtual inputs.
- The protection logic has not been validated on physical hardware.

The project demonstrates protection concepts and should not be considered a certified motor protection system.

## 🚀 Future Enhancements

- Integration with an ESP32 microcontroller.
- Real-time current measurement using a suitable current sensor.
- Rotor-speed measurement using Hall-effect sensors.
- Real-time motor telemetry.
- Voltage and temperature monitoring.
- Hardware-based motor shutdown.
- Back EMF modelling and analysis.
- Graphical monitoring of current and speed.

## 👨‍💻 Project Information

**Project Title:** Overcurrent and Stall Protection for BLDC Motor Drive

**Project Name:** DriveGuard Lab

**Project Type:** Software-Based Mini Project

**Department:** Electrical and Electronics Engineering

**Institution:** Kalasalingam Academy of Research and Education

**Course:** EEE206 – Electrical Machines Laboratory-I

## 📜 License

This project is intended for educational and academic demonstration purposes.

---

**DriveGuard Lab – Making BLDC Motor Protection Concepts Easier to Understand.**
