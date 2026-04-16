# Digital Fairy Companion
## 1. Description of the functionality
The Digital Fairy Companion functions as a reactive embedded system that translates environmental data into interactive emotional responses to simulate a sentient digital presence. By continuously monitoring real-time inputs from light, motion, sound, color sensors and by capacitive touch interaction, the system utilizes a complex Finite State Machine to manage over seventeen distinct behavioral states. These inputs are processed by an STM32 Nucleo microcontroller which autonomously coordinates visual animations on a 2.4-inch LCD, synchronized audio responses stored on a microSD card, and dynamic ambient lighting via RGB LEDs. In practice, the system adapts its persona based on environmental triggers, such as entering a sleep state in low light or initiating a productivity timer when specific colors are detected, providing a comprehensive multi-sensory user experience.

## 2. Motivation
I chose this project because of a deep conviction that mood and mental well-being are fundamental pillars for personal growth and resilience in daily life. By merging the technical rigor of embedded systems with the whimsical charm of childhood nostalgia, I aimed to recreate the sense of magic that is often absent in standard modern technology. This project serves as a bridge between the complex mechanics of real-time sensor processing and the emotional human experience, providing a supportive companion that acknowledges and reacts to its user's environment. Ultimately, developing this system from the ground up allows me to explore how hardware and software can be harnessed not just for utility, but to foster a more mindful and enchanting atmosphere within a personal workspace.

## 3. Architecture
### Components and Interconnection
The Digital Fairy Companion is structured into three primary functional modules that work in tandem to create an interactive experience:
* **Sensory Module**

  This layer is responsible for environmental data acquisition. It utilizes a TCS34725 for color identification, an MPU 6050 for motion and rhythm detection, a photoresistor for light intensity, an analog microphone for sound levels, and a TTP223 capacitive sensor for touch interaction. These sensors are connected to the central unit using a mix of I2C, SPI, and ADC interfaces.

* **Processing & Logic Module**

  At the core of the system sits the NUCLEO-U545RE-Q microcontroller, which implements a Finite State Machine (FSM) to manage over 17 distinct emotional states. It evaluates incoming sensor data to determine the appropriate behavior, such as switching from "Sleepy" to "Scared" based on sudden light and sound changes.

* **Feedback & Enclosure Module**

  The system produces outputs through a 2.4-inch ILI9341 LCD for pixel-art animations, a PAM8403 amplifier paired with a 1W speaker for audio, and WS2812 RGB LEDs for status-based lighting. The entire system is integrated into a thematic "Fairy House" enclosure, where the screen acts as a window and sensors are strategically hidden in decorative elements like an entrance flower or the roof.

### Data & Logic Flow
Data enters the system through various protocols: I2C for complex sensory modules (Color and IMU) and SPI for high-speed communication with the LCD and SD card. The microcontroller performs real-time analysis of these inputs to trigger state transitions. Once a state is identified, the MCU retrieves corresponding graphical frames and audio clips from the microSD card and updates the visual and auditory outputs simultaneously.

## 4. Hardware Design
### Hardware Description
Each component was selected to balance high performance with the low-power requirements of an always-on companion device:
* **Microcontroller (MCU)**

  The NUCLEO-U545RE-Q was chosen for its ultra-low-power capabilities and sufficient processing power to handle multiple serial protocols and complex FSM logic concurrently.

* **Display & Storage**

  The ILI9341 LCD module was selected for its vibrant color reproduction and integrated microSD slot, which simplifies the wiring for the SPI bus while providing ample storage for pixel-art assets.

* **Sensors**

  The TCS34725 provides superior color accuracy via I2C, while the MPU 6050 (GY-521) offers 3-axis precision for detecting physical interaction or "dizziness". The TTP223 capacitive touch sensor allows for a seamless "petting" interface without mechanical wear.

* **Audio Subsystem**

  To provide clear auditory feedback, the PAM8403 Class D amplifier is used to drive a compact 1W 8ohm speaker, delivering high-efficiency sound reproduction directly from the board's DAC.

* **Prototyping & Power**

  The system is assembled on an MB102 830-point breadboard using a combination of male-to-female and male-to-male jumper wires. Power is supplied through the USB connection of the Nucleo board, ensuring a stable 5V and 3.3V supply for all modules.

## 5. Software Design

## 6. Bill of Materials (BOM)

## 7. Weekly Log
