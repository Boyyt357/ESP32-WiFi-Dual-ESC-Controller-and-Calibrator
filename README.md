This project provides a simple and effective way to control two SimonK-compatible Electronic Speed Controllers (ESCs) wirelessly using an ESP32 microcontroller. The ESP32 acts as a WiFi Access Point and hosts a web server with a user-friendly interface to control the throttle of both ESCs simultaneously.

Features
WiFi Access Point: The ESP32 creates its own network, so no external router is needed. This makes it ideal for remote control applications.

Web Server: A web server with a clean, responsive HTML interface is hosted on the ESP32, allowing control from any device with a web browser (e.g., a smartphone, tablet, or computer).

Dual ESC Control: Control two ESCs with a single slider, making it perfect for applications like RC cars, boats, or robotics that require synchronized motor control.

Dynamic PWM Configuration: The web interface allows you to set custom minimum and maximum PWM pulse widths (in microseconds) to match the calibration of your specific ESCs.

Safety: The code includes safety checks to constrain the PWM values and ensures a default minimum throttle on startup.

Prerequisites
Before you can use this project, you will need the following:

Hardware
An ESP32 development board (e.g., ESP32-WROOM-32).

Two SimonK-compatible ESCs.

Two brushless motors (connected to the ESCs).

A suitable power supply for the ESCs and motors (do NOT power the ESCs from the ESP32's 5V pin).

Software
Arduino IDE: With the ESP32 board support package installed.

Libraries: You must install the following libraries via the Arduino Library Manager:

ESPAsyncWebServer

AsyncTCP

ESP32Servo

Library Installation Steps
In the Arduino IDE, go to Sketch > Include Library > Manage Libraries....

Search for and install ESPAsyncWebServer.

Search for and install AsyncTCP.

Search for and install ESP32Servo.

Hardware Setup (Wiring)
Power: Connect the main power supply (e.g., a battery pack) to your ESCs. Be sure to connect the ground of this power supply to a GND pin on your ESP32 to ensure a common ground.

ESC 1 Signal: Connect the signal wire of the first ESC to GPIO 2 on the ESP32.

ESC 2 Signal: Connect the signal wire of the second ESC to GPIO 4 on the ESP32.

Motors: Connect your brushless motors to the three output wires of each ESC.

Warning: Do not connect the BEC (Battery Eliminator Circuit) power wire from the ESC to your ESP32's power pins if the ESC's voltage output is greater than 5V. It is safer to use a separate 5V regulator or power the ESP32 via USB and ensure a common ground.

Usage
Upload the Code: Open the sketch_aug2a.ino file in the Arduino IDE and upload it to your ESP32 board.

Connect to the Network:

On your computer, smartphone, or tablet, go to your WiFi settings.

Find and connect to the network named "ESP32-ESC-AP".

The password is "password123".

Access the Web Interface:

Open a web browser (e.g., Chrome, Firefox, Safari).

Navigate to the IP address 192.168.4.1.

You should see the ESC controller interface.

Control the ESCs:

Use the Min PWM (µs) and Max PWM (µs) input fields to set the throttle range.

Use the main Throttle Control slider to adjust the PWM signal for both ESCs simultaneously. The value is displayed next to the slider.
