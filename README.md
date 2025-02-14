# Humanoid Robot Walking Motion with 6 Servos

## Overview
This project simulates a walking motion for a humanoid robot using 6 servo motors. The robot uses 2 servos for each leg (one for the knee and one for the ankle), and 2 additional servos for the waist to assist with balance and stability. The walking cycle alternates between the two legs, with one leg swinging forward while the other remains flat on the ground for support.

## Algorithm Steps

### 1. **Initialization:**
- Set all motors (hip, knee, and ankle) to the neutral position (e.g., 90°).
- The robot should stand upright and stable.

### 2. **Balance Check:**
- Continuously monitor the robot’s balance using sensors (e.g., gyroscope, accelerometer).
- Ensure the robot’s center of gravity (CoG) is over the supporting leg to avoid falling.

### 3. **Shift Weight to One Leg:**
- Lift one leg off the ground by moving the knee and adjusting the ankle.
- The opposite leg remains flat on the ground, with the knee slightly bent to provide support.

### 4. **Swing the Leg:**
- Move the lifting leg forward using the knee motor.
- The ankle motor adjusts the foot placement, ensuring the foot does not drag on the ground.

### 5. **Landing:**
- As the foot moves toward the ground, use the ankle motor to place it flat on the ground.
- The supporting leg absorbs the impact with a slight knee bend.

### 6. **Shift Weight to the New Leg:**
- Shift the weight to the newly planted leg.
- Lift the other leg (now the swing leg) and repeat the process.

### 7. **Repeat the Walking Cycle:**
- Alternate between the two legs: one leg swings while the other stays on the ground for support.

### 8. **Adjust Walking Speed:**
- To walk faster, shorten the time spent in each step phase (swing and stance).
- To walk slower, increase the time spent in each phase.

### 9. **Continuous Balance Adjustment:**
- Continuously adjust the waist position to maintain balance while walking.
- The waist helps keep the upper body stable and aligned with the legs.

## Code Explanation

### **Servo Initialization:**
- The servos are initialized to the neutral position (90°) where the robot stands upright.
- The `setStandingPosition()` function sets all the servos to this position at the start.

### **Balance Check:**
- The `balanceCheck()` function is called when shifting weight from one leg to another. It adjusts the waist motor to ensure balance.

### **Weight Shift:**
- The `shiftWeightToLeg()` function handles shifting weight to one leg while preparing the other leg to lift.

### **Leg Swing:**
- The `swingLeg()` function moves the lifted leg forward using the knee motor, while the ankle motor adjusts the foot placement.

### **Foot Landing:**
- The `landFoot()` function places the foot flat on the ground, and the knee slightly bends to absorb the impact.

### **New Leg Shift:**
- The `shiftToNewLeg()` function moves the robot back to the neutral position after the leg lands, allowing the robot to prepare for the next step.

### **Walking Cycle:**
- The entire process of alternating between the two legs happens continuously in the `walkingCycle()` function.

### **Speed Control:**
- Adjust the walking speed by modifying the `delay(100)` in the `loop()` function. Shorten the delay for faster walking and increase it for slower walking.


## **Wiring:**
   - Connect the servos to their respective pins on the Arduino (2 for each leg and 2 for the waist).
   - Ensure proper power supply for the servos.
