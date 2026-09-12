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
- ESP8266
#### Sensor
- LM35 temperature sensor
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

### IoT & Networking
- MQTT Publish/Subscribe architecture
- MQTT QoS
- MQTT Client ID management
- MQTT topic design
- ThingSpeak cloud integration
- ThingSpeak React
- ThingHTTP
- REST API
- DNS troubleshooting
- MQTT diagnostics
### Embedded Systems
- Arduino UNO / ATmega328P
- LM35 sensor interfacing
- Analog temperature measurement
- DC motor control
- Event-driven firmware
- Embedded system simulation
### Simulation
- Proteus 9.1 VSM
- Proteus Visual Designer
- IoT simulation
- Flowchart-based firmware development
### Tools
- Mosquitto MQTT
- mosquitto_pub
- mosquitto_sub
- nslookup
### Engineering & Problem Solving
- Layer-by-layer debugging
- Root cause analysis
- Cloud integration troubleshooting
- Communication troubleshooting
- Technical documentation

## My Contribution

- Designed the complete IoT architecture from sensor to cloud
- Configured and tested MQTT communication
- Configured ThingSpeak channel and fields
- Created separate MQTT publish and subscribe devices
- Developed Proteus Visual Designer flowcharts
- Implemented temperature publishing and motor command subscription
- Configured ThingSpeak React rule engine and ThingHTTP REST API action
- Designed ThingSpeak dashboard
- Performed DNS and MQTT diagnostics
- Tested MQTT communication using Mosquitto CLI
- Debugged broker, credentials, topic and flowchart issues
- Validated complete end-to-end IoT communication
- Documented architecture, testing and engineering challenges

## Key Engineering Learnings

- MQTT is a communication protocol and can be used with different MQTT clients and brokers.
- ThingSpeak provides MQTT, cloud storage, visualization and rule-based automation within one platform.
- ThingSpeak uses a specific MQTT topic structure for channel fields.
- Separate MQTT credentials/devices can be required for independent publish and subscribe operations.
- Continuous subscription handling is important for receiving MQTT commands.
- Cloud-based automation introduces additional response latency compared with local control.
- MQTT, ThingHTTP and ThingSpeak API keys have different purposes.
- Testing individual communication layers before performing end-to-end testing simplifies debugging.

## Results

The system successfully achieved:
Temperature Sensing → MQTT Publishing → ThingSpeak Cloud → React Rule → ThingHTTP → MQTT Subscription → Motor Control
This project demonstrates practical experience in embedded systems, IoT communication, MQTT, cloud integration, simulation, debugging and automation.
