# Robot-Walking-Algorithm-with-Servo-Motors
The algorithm controls servo motors to make a robot walk. It starts by setting up initial servo positions and then directs specific leg movements—lifting, advancing, and placing each leg down—while ensuring balanced weight distribution between legs. This sequence repeats continuously to maintain a walking motion.

- SET_SERVO_ANGLE(motor, angle): This function sets the angle of the specified servo motor.
- PAUSE(milliseconds): This function pauses the execution for a specified time in milliseconds.

## 1. Set initial positions for all servos to the standing posture

```plaintext
INITIALIZE_SERVO_POSITIONS()
    SET_SERVO_ANGLE(motor1, 0)
    SET_SERVO_ANGLE(motor2, 0) 
    SET_SERVO_ANGLE(motor3, 0)
    SET_SERVO_ANGLE(motor4, 0)
    SET_SERVO_ANGLE(motor5, 0)
    SET_SERVO_ANGLE(motor6, 0)
```
## 2. PERFORM_STEP
- Step 1: Lift left leg: Move the left hip forward, bend the left knee, and adjust the left ankle to lift the left leg.

```plaintext
    SET_SERVO_ANGLE(motor1, 30)  # Move left hip forward
    SET_SERVO_ANGLE(motor3, 60)  # Bend left knee
    SET_SERVO_ANGLE(motor5, -10)  # Adjust left ankle
    PAUSE(500)
```

- Step 2: Move left leg forward: Move the left hip further forward, slightly straighten the left knee, and adjust the left ankle back to neutral to move the left leg forward.

```plaintext
    SET_SERVO_ANGLE(motor1, 60)  # Move left hip further forward
    SET_SERVO_ANGLE(motor3, 30)  # Slightly straighten left knee
    SET_SERVO_ANGLE(motor5, 0)   # Adjust left ankle back to neutral
    PAUSE(500)
```

- Step 3: Place left leg down: Move the left hip to the step position, straighten the left knee completely, and adjust the left ankle for stability to place the left leg down.

```plaintext
    SET_SERVO_ANGLE(motor1, 90)  # Move left hip to step position
    SET_SERVO_ANGLE(motor3, 0)   # Straighten left knee completely
    SET_SERVO_ANGLE(motor5, 10)  # Adjust left ankle for stability
    PAUSE(500)
```

- Step 4: Shift weight to left leg: Move the right hip backward, bend the right knee, and adjust the right ankle to shift weight to the left leg.

```plaintext
    SET_SERVO_ANGLE(motor2, -30)  # Move right hip backward
    SET_SERVO_ANGLE(motor4, 60)   # Bend right knee
    SET_SERVO_ANGLE(motor6, -10)  # Adjust right ankle
    PAUSE(500)
```

- Step 5: Lift right leg: Move the right hip further backward, slightly straighten the right knee, and adjust the right ankle back to neutral to lift the right leg.

```plaintext
    SET_SERVO_ANGLE(motor2, -60)  # Move right hip further backward
    SET_SERVO_ANGLE(motor4, 30)   # Slightly straighten right knee
    SET_SERVO_ANGLE(motor6, 0)    # Adjust right ankle back to neutral
    PAUSE(500)
```

- Step 6: Move right leg forward: Move the right hip to the step position, straighten the right knee completely, and adjust the right ankle for stability to move the right leg forward.

```plaintext
    SET_SERVO_ANGLE(motor2, -90)  # Move right hip to step position
    SET_SERVO_ANGLE(motor4, 0)    # Straighten right knee completely
    SET_SERVO_ANGLE(motor6, 10)   # Adjust right ankle for stability
    PAUSE(500)
```

- Step 7: Place the right leg down and shift weight back to neutral: Return all servos to the neutral position to place the right leg down and prepare for the next step.

```plaintext
    SET_SERVO_ANGLE(motor1, 0)   # Return left hip to neutral
    SET_SERVO_ANGLE(motor2, 0)   # Return right hip to neutral
    SET_SERVO_ANGLE(motor3, 0)   # Straighten left knee completely
    SET_SERVO_ANGLE(motor4, 0)   # Straighten right knee completely
    SET_SERVO_ANGLE(motor5, 0)   # Adjust left ankle to neutral
    SET_SERVO_ANGLE(motor6, 0)   # Adjust right ankle to neutral
    PAUSE(500) 
```

## Main Loop 

```plaintext
MAIN_LOOP()
    INITIALIZE_SERVO_POSITIONS()
    WHILE (TRUE):
        PERFORM_STEP()
```

- INITIALIZE_SERVO_POSITIONS(): Call the function to set all servos to their initial positions.
- WHILE (TRUE): Continuously repeat the walking motion by calling PERFORM_STEP() in an infinite loop.
