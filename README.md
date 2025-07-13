
RFID-based-attendance-system-using-Arduino
==========================================

[![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=Arduino&logoColor=white)](https://www.arduino.cc/) [![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)](https://isocpp.org/) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

A complete **RFID-based attendance system using Arduino** that automates employee and student attendance tracking with real-time logging, LCD display, and offline data storage capabilities.

 <img width="750" height="500" alt="RFID-Based-Attendance-System-Using-Arduino" src="https://github.com/user-attachments/assets/131318af-f3c3-4f16-b017-6e14d19fd176" />

🚀 Features
-----------

-   **Automatic Check-in/Check-out Detection** - Smart status tracking based on last entry
-   **Real-time Clock Integration** - Precise timestamps with DS1307 RTC module
-   **Offline Data Storage** - 30+ attendance logs stored in EEPROM memory
-   **LCD Interface** - 16x2 I2C display with scrolling names and live people count
-   **Card Programming Utility** - Easy RFID card setup with personal data
-   **Serial Monitor Control** - Full system control via Arduino IDE
-   **Power Loss Protection** - Data retention during power outages
-   **Cost-Effective** - Under $35 total build cost vs $500+ commercial systems


🛠️ Hardware Requirements
-------------------------

### Primary Components

-   **Arduino Uno** (1x) - ATmega328P microcontroller board
-   **MFRC522 RFID Module** (1x) - 13.56MHz RFID reader with SPI interface
-   **DS1307 RTC Module** (1x) - Real-time clock with AT24C32 EEPROM
-   **16x2 I2C LCD Display** (1x) - HD44780 compatible with I2C backpack
-   **Push Buttons** (2x) - 6x6mm tactile buttons for navigation
-   **RFID Cards/Tags** - Mifare Classic 1K, 13.56MHz
-   **Breadboard** (1x) - Full-size for prototyping
-   **Jumper Wires** - Male-to-male connections
-   **Power Supply** - 5V-12V DC adapter or battery

### Optional Components

-   **Buzzer** - Audio feedback for card scans
-   **LED Indicators** - Visual status indicators
-   **SD Card Module** - Additional storage backup
-   **Ethernet Shield** - Network connectivity

📐 Circuit Diagram
------------------

```
Arduino Uno Connections:
┌─────────────────┬──────────────────┬────────────────┐
│ Arduino Pin     │ Component        │ Function       │
├─────────────────┼──────────────────┼────────────────┤
│ Digital Pin 7   │ MFRC522 RST      │ RFID Reset     │
│ Digital Pin 8   │ Menu Button      │ Navigation     │
│ Digital Pin 9   │ Select Button    │ Confirmation   │
│ Digital Pin 10  │ MFRC522 SS       │ SPI Slave Sel. │
│ Digital Pin 11  │ MFRC522 MOSI     │ SPI Data Out   │
│ Digital Pin 12  │ MFRC522 MISO     │ SPI Data In    │
│ Digital Pin 13  │ MFRC522 SCK      │ SPI Clock      │
│ Analog Pin A4   │ SDA              │ I2C Data       │
│ Analog Pin A5   │ SCL              │ I2C Clock      │
└─────────────────┴──────────────────┴────────────────┘

```

⚙️ Installation
---------------

### 1\. Arduino IDE Setup

```
# Install required libraries via Arduino Library Manager:
# - MFRC522 by GithubCommunity
# - RTClib by Adafruit
# - LiquidCrystal I2C by Frank de Brabander

```

### 2\. Hardware Assembly

1.  Connect components according to the circuit diagram
2.  Ensure proper power distribution (5V/3.3V compatibility)
3.  Verify I2C addresses (LCD: 0x27, RTC: 0x68, EEPROM: 0x50)

### 3\. Code Upload

```
git clone https://github.com/krishnajiMottadi/RFID-Based-Attendance-System-Using-Arduino.git
cd RFID-Based-Attendance-System-Using-Arduino

```

1.  **First**: Upload `ReadandWrite_PersonalData.ino` to program RFID cards
2.  **Second**: Upload `RFIDAttendanceSystem_Main.ino` for main operation

🎯 Usage
--------

### Programming RFID Cards

1.  Upload the card programming sketch
2.  Open Serial Monitor (9600 baud)
3.  Type `w` for write mode
4.  Place the RFID card near the reader
5.  Enter name (max 32 characters)
6.  Enter ID (max 8 characters)
7.  Verify with read mode (`r`)

### Operating the Attendance System

1.  Upload the main attendance code
2.  Set correct time via Serial Monitor (`t` command)
3.  Present programmed RFID cards to the reader
4.  The system automatically tracks IN/OUT status
5.  View logs via buttons or Serial Monitor commands

### Serial Commands

-   `v` - View all attendance logs
-   `c` - Clear all logs
-   `s` - System status
-   `t` - Set time


### Key Functions

-   `handleRFIDScan()` - Processes card detection and logging
-   `handleButtons()` - Manages menu navigation
-   `displayHomeScreen()` - Updates LCD with time/status
-   `logAttendance()` - Stores records in EEPROM
-   `readPersonalData()` - Retrieves card information


📱 Applications
---------------

### Educational Institutions

-   **Student Attendance** - Automated classroom tracking
-   **Library Access** - Book borrowing management
-   **Hostel Entry** - Secure dormitory access

### Corporate Environments

-   **Employee Time Tracking** - Work hour monitoring
-   **Meeting Room Access** - Conference room management
-   **Visitor Management** - Guest entry logging

### Industrial Settings

-   **Shift Management** - Worker schedule tracking
-   **Safety Compliance** - Restricted area monitoring
-   **Contractor Access** - Temporary worker management

🔮 Future Enhancements
----------------------

-   [ ] **WiFi Connectivity** - ESP8266 integration for IoT capabilities
-   [ ] **Mobile App** - Android/iOS app for remote monitoring
-   [ ] **Biometric Security** - Fingerprint sensor integration
-   [ ] **Camera Module** - Photo capture for verification
-   [ ] **Database Integration** - MySQL/MongoDB connectivity
-   [ ] **Multi-Location** - Network multiple units
-   [ ] **Access Control** - Door lock integration
-   [ ] **Web Dashboard** - Real-time monitoring interface

🏗️ Technical Specifications
----------------------------

| Parameter | Value |
| --- | --- |
| Operating Voltage | 5V DC |
| Current Consumption | 150-200mA (active) |
| RFID Frequency | 13.56MHz |
| Reading Range | 1-3cm |
| Storage Capacity | 30 logs (expandable) |
| Clock Accuracy | ±2 minutes/month |
| Operating Temperature | 0°C to 50°C |
| Response Time | <500ms |

