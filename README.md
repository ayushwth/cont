# Slide Control with Flutter and NodeJS via WebSocket

This project allows remote control of a **slideshow** (or any other software) by simulating **mouse** and **keyboard** movements through a Flutter app connected via **WebSocket** to a NodeJS server. The Flutter app uses the device’s **accelerometer** and **gyroscope** sensors to detect movement, providing a smooth experience for navigating slides or performing actions remotely.

## Features

- Remote control of slide presentations.
- Simulation of mouse movements and keyboard actions.
- Real-time connection between **NodeJS** and the **Flutter** app via **WebSocket**.
- Uses **accelerometer** and **gyroscope** sensors to detect movements.
- Ideal for controlling presentations while away from the device.

## Requirements

### Server (NodeJS)

- Node.js (v14.x or higher)
- WebSocket
- Libraries for simulating mouse and keyboard actions

### App (Flutter)

- Flutter SDK (v2.0 or higher)
- `sensors_plus` plugin to access device sensors
- WebSocket for server communication

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/cl0v/tv-controller
cd tv-controller
```

### 2. Set Up the NodeJS Server

Install NodeJS dependencies:

```bash
cd nodejs
npm install
```

### 3. Start the WebSocket Server

```bash
npm run start
```

### 4. Set Up the Flutter App

Make sure Flutter is installed and dependencies are configured:

```bash
cd flutter
flutter pub get
```

### 5. Run the Flutter App

Connect a device or use an emulator to run the app:

```bash
flutter run
```

## How It Works

### NodeJS Server

The NodeJS server receives commands from the Flutter app via WebSocket and simulates mouse and keyboard actions on the host system. Based on the data sent from the accelerometer and gyroscope, the server performs the following:

- **Mouse Movement**: Based on the tilt and motion of the device.
- **Slide Forward/Backward**: Using specific gestures or tilts to send keyboard commands (e.g., `left arrow` and `right arrow` keys).

### Flutter App

The app collects motion data through the sensors (accelerometer/gyroscope) and sends it to the NodeJS server via WebSocket. The server interprets this data and converts it into mouse/keyboard commands.

## Usage Examples

### Left/Right Movement

- Tilt the device to the left to simulate pressing the **left arrow** key.
- Tilt the device to the right to simulate pressing the **right arrow** key.

### Mouse Movement

- Gentle movements on the **X** or **Y** axis of the gyroscope can be used to move the mouse cursor.

## Screenshots

![Usage Example](/screenshots/output.gif)

## Technologies Used

- **NodeJS**: Manages the WebSocket server and handles mouse/keyboard actions.
- **WebSocket**: Enables real-time communication between the server and the Flutter app.
- **Flutter**: Captures accelerometer and gyroscope data and sends it to the server.
- **sensors_plus**: Flutter plugin for accessing sensors like accelerometer and gyroscope.
- **robotjs**: NodeJS library for simulating mouse and keyboard actions.

## Contributing

1. Fork the project
2. Create a branch for your feature (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Open a Pull Request


## License

This project is licensed under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0).

## Contact

If you have questions or suggestions, feel free to open an **issue** or reach out via [LinkedIn](https://www.linkedin.com/in/marcelo-fernandes-viana-a49311329/).

### Project Structure

- **nodejs/**: Contains the NodeJS server code.
- **flutter/**: Contains the Flutter app code.
