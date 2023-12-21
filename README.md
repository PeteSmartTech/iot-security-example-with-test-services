# iot-security-example-with-test-services

Project was developed for scholar purposes.
The whole idea was to suggest a solution for securing the IoT systems.

# Project Overview
## Idea and Objective:
I aimed to create a system for IoT devices, specifically Raspberry Pi's, to securely register and communicate with a central server.
The primary goals were secure device provisioning, management and transmission of weather data collected by these devices.

## Implementation and Delivery

### WireGuard Provisioning Service (WGPS):

- Developed a Python-based service for device registration and management.
- Utilized WireGuard for secure VPN tunneling to ensure encrypted communication.
- Implemented token-based authentication for device registration.
- Established a mechanism to dynamically assign IP addresses to devices and store their details in a database.


### Weather Data Service:

- Built a service to receive, store, and retrieve weather data sent by edge devices.
- Ensured data transmission over secure channel. (through the WireGurad tunnel only)
- Employed a database to store weather data along with device information.
- Provided endpoints for data submission and retrieval, with authentication based on a hashed special device token.


### Client Application on Raspberry Pi:

- Developed a client-side application for Raspberry Pi to gather and send weather data.
- Scripted automatic setup procedures, including WireGuard configuration, device ID generation, and secure token handling.
- Implemented functionality to hash the special device token before transmission for added security.
- Addressed various challenges related to Docker containerization and network communication within the secure tunnel.


### Dockerization and Network Configuration:

- Containerized the server-side applications using Docker for isolation and ease of deployment.
- Configured Docker Compose for managing multi-container Docker applications, ensuring correct network setup for inter-container communication.
- Dealt with challenges in setting up WireGuard within a Docker environment and ensuring proper network interfaces and permissions.


### Security Measures:

- Emphasized secure communication channels using WireGuard VPN (delivered) and SSL/TLS encryption (in real-world scenario, suggested via reverse-proxy to enroll the edge device).
- Implemented token-based authentication and token hashing for secure device registration and data transmission.
- Utilized firewall rules on Raspberry Pi to restrict traffic, allowing only essential communication.
- Ensured secure handling and storage of sensitive data like tokens and device IDs.


### Simulating the data collection
The edge devices should collect real metrics, however for test-purposes there was written a script that simulates collection of authentic weather data.

### License
Feel free to do whatever You want with this code.

This piece of software is under the WTFPL license.