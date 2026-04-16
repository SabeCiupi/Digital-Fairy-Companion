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
