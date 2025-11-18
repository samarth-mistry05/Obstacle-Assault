# Obstacle Assault

A dynamic obstacle course game built with Unreal Engine featuring moving and rotating platforms that challenge players to navigate through increasingly difficult terrain.

## Overview

Obstacle Assault is an Unreal Engine C++ project that implements a physics-based platforming experience. Players must time their movements carefully to traverse platforms that move and rotate in various patterns.

## Features

- **Dynamic Moving Platforms**: Platforms that move back and forth along customizable paths
- **Rotating Obstacles**: Platforms with configurable rotation velocities
- **Customizable Parameters**: Easy-to-adjust platform behaviors through Unreal's Blueprint editor
- **Smooth Movement**: Delta-time based movement for consistent performance across different frame rates

## Technical Details

### Moving Platform System

The core gameplay revolves around the `AMovingPlatform` actor class, which provides:

- **Velocity-based Movement**: Platforms move along a defined direction with customizable speed
- **Automatic Return**: Platforms reverse direction when reaching their maximum distance
- **Rotation Support**: Independent rotation system that can be combined with translation
- **Editor-friendly**: All parameters exposed to Unreal's editor for easy level design

### Key Parameters

- `PlatformVelocity` (FVector): Direction and speed of platform movement
- `MoveDistance` (float): Maximum distance the platform travels before reversing
- `RotationVelocity` (FRotator): Rotation speed around each axis

## Project Structure

```
obstacleAssault/
├── Source/
│   └── obstacleAssault/
│       ├── MovingPlatform.h
│       ├── MovingPlatform.cpp
│       ├── obstacleAssault.h
│       ├── obstacleAssault.cpp
│       └── obstacleAssault.Build.cs
```

## Requirements

- Unreal Engine (version compatible with the project)
- C++ compiler (Visual Studio 2019/2022 for Windows, Xcode for macOS)
- Basic understanding of Unreal Engine's Actor system

## Setup

1. Clone this repository
2. Right-click the `.uproject` file and select "Generate Visual Studio project files"
3. Open the generated solution file
4. Build the project
5. Launch the project through the Unreal Editor

## Usage

### Adding Moving Platforms to Your Level

1. In the Unreal Editor, find `AMovingPlatform` in the Content Browser
2. Drag it into your level
3. Select the platform and adjust the following properties in the Details panel:
   - **Platform Velocity**: Set the direction and speed (e.g., `(100, 0, 0)` for X-axis movement)
   - **Move Distance**: Set how far the platform travels before reversing
   - **Rotation Velocity**: Set rotation speed for each axis (optional)

### Example Configurations

**Horizontal Moving Platform:**
- Platform Velocity: `(200, 0, 0)`
- Move Distance: `500`

**Rotating Platform:**
- Platform Velocity: `(0, 0, 0)`
- Rotation Velocity: `(0, 0, 45)` for Z-axis rotation

**Combined Movement:**
- Platform Velocity: `(150, 100, 0)`
- Move Distance: `400`
- Rotation Velocity: `(0, 15, 0)`

## Code Highlights

The platform movement logic efficiently handles direction reversal by:
1. Calculating the distance traveled from the start position
2. Reversing velocity when the distance exceeds the configured threshold
3. Adjusting the start location to maintain smooth bi-directional movement

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

## License

This project is provided as-is for educational and development purposes.

## Acknowledgments

Built using Unreal Engine's powerful C++ framework for game development.
