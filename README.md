# IoT-Temperature-Monitoring-Automatic-Motor-Control-Using MQTT and ThingSpeak
Flowchart-based firmware development 

## Project Overview
This project demonstrates an end-to-end Internet of Things (IoT) system for real-time temperature monitoring and automatic motor control.
An LM35 temperature sensor is interfaced with an Arduino UNO using a simulation software. Temperature data is transmitted to the ThingSpeak cloud platform using the MQTT protocol through an ESP8266 Wi-Fi module.
A ThingSpeak React rule engine continuously evaluates the temperature data. When the temperature exceeds the defined threshold of 28°C, a ThingHTTP request updates the motor-control field. The command is then received by a second MQTT client in the Proteus simulation, causing the DC motor to start.

Note: The embedded hardware and firmware execution are simulated in Proteus 9.1 VSM, while the MQTT communication and ThingSpeak cloud interaction are real.

## Technologies Used

### Hardware / Simulation Components: 
#### Microcontroller
- Arduino UNO
- ATmega328P
- Proteus 9.1 VSM simulation
#### Sensor
- LM35 temperature sensor
- Analog output
- 10 mV/°C sensitivity
- Connected to Arduino Analog Pin A0
#### Communication
- ESP8266 Wi-Fi module
- Proteus ESP1:MQTT component
- MQTT communication with ThingSpeak
#### Actuator
- DC Motor
- Motor driver
- Motor runs in FORWARDS direction at speed 255 when the ON command is received

 
## System Architecture

The project therefore demonstrates the complete IoT flow:
Sensing → Connectivity → MQTT → Cloud → Rule Engine → Command → Actuation

## Key Features

- Real-time temperature monitoring using an LM35 sensor
- Arduino UNO / ATmega328P based embedded system
- ESP8266-based MQTT communication
- ThingSpeak cloud integration
- MQTT publish/subscribe architecture
- Separate MQTT devices for publishing and subscribing
- Automatic motor control based on temperature threshold
- ThingSpeak React rule engine
- ThingHTTP REST API integration
- ThingSpeak dashboard visualization
- Proteus 9.1 VSM IoT simulation
- MQTT testing using mosquitto_pub and mosquitto_sub
- End-to-end debugging and validation


## Skills Demonstrated

- STM32F401RE microcontroller
- Embedded C
- Proteus VSM simulation
- ADC
- UART communication
- Sensor interfacing
- Debugging and testing

## My Contribution

- Designed the overall IoT system architecture
- Selected the STM32F446RE, Raspberry Pi 3B, MQ135 and MQ7
- Developed Embedded C firmware for STM32
- Implemented ADC-based sensor reading
- Implemented sensor range classification
- Developed Raspberry Pi Python GPIO interface
- Integrated the system with ThingSpeak
- Configured remote Raspberry Pi access using VNC
- Performed hardware testing and debugging / Debugged hardware/firmware interaction.

## Engineering Challenges

### Challenge 1 — Noisy low-cost sensor output

The MQ135 and MQ7 sensors produce noisy analog output and do
not directly provide reliable PPM values.

### Solution

Implemented an 8-bit ADC-based three-band classification approach
to provide indicative pollution severity levels.

### Challenge 2 — Limited communication pins

The STM32 needed to communicate the classified sensor status
to the Raspberry Pi using limited GPIO resources.

### Solution

Used two digital GPIO signals per sensor to encode the
three classification bands.

## Limitations

The current prototype provides indicative pollution severity
levels rather than calibrated PPM measurements.

The MQ135/MQ7 output is classified into predefined ranges.
Future work will include proper sensor calibration and
PPM conversion.

## Results

The system successfully transmitted sensor readings from the
STM32 through the Raspberry Pi gateway to ThingSpeak.

The ThingSpeak dashboard displayed the sensor data as live
field charts at approximately 15-second intervals.

