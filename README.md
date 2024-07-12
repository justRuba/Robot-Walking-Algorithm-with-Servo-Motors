# Robot-Walking-Algorithm-with-Servo-Motors
The algorithm controls servo motors to make a robot walk. It starts by setting up initial servo positions and then directs specific leg movements—lifting, advancing, and placing each leg down—while ensuring balanced weight distribution between legs. This sequence repeats continuously to maintain a walking motion.

## Initialize servo positions to starting posture

```plaintext
INITIALIZE_SERVO_POSITIONS()
    SET_SERVO_ANGLE(left_hip, NEUTRAL_POSITION)   
    SET_SERVO_ANGLE(right_hip, NEUTRAL_POSITION)
    SET_SERVO_ANGLE(left_knee, STRAIGHT_POSITION) 
    SET_SERVO_ANGLE(right_knee, STRAIGHT_POSITION)
    SET_SERVO_ANGLE(left_ankle, NEUTRAL_POSITION) 
    SET_SERVO_ANGLE(right_ankle, NEUTRAL_POSITION)
```

*Sets all servo motors to their starting positions*
- NEUTRAL_POSITION for hips and ankles.
- STRAIGHT_POSITION for knees.
