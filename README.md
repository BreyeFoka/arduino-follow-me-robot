# Arduino follow-me robot

A four-wheel Arduino Uno robot that follows a person or an object. An ultrasonic sensor keeps it at a set distance and two infrared sensors steer it left or right.

## How it follows

| Sensors | Robot |
| --- | --- |
| Something 1–15 cm ahead (ultrasonic) | Drives forward |
| Only the left IR sensor sees it | Turns left |
| Only the right IR sensor sees it | Turns right |
| Nothing within 15 cm | Stops |

At start-up the servo sweeps the sensor mount left and right once.

## Hardware

| Part | Connection |
| --- | --- |
| Arduino Uno with an Adafruit Motor Shield (v1) | |
| 4 DC motors | Motor shield ports M1–M4 |
| HC-SR04 ultrasonic sensor | Trigger A1, Echo A0 |
| IR sensors | Right A2, Left A3 |
| Servo | Pin 10 |

## Build

Install the **Adafruit Motor Shield library** (v1, `AFMotor.h`), **NewPing** and **Servo** libraries, then upload `Arduino_Follow_Me_Robot.ino` to the Uno. GitHub Actions compiles the sketch on every push.

## Limitations

- Fixed speed and distances; tuning means editing the sketch.
- Infrared sensors are affected by sunlight and dark clothing.
