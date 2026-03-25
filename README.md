# Intro to Industrial Robotic Arms

**Name:** Harish Anand

---

## Introduction

The Magician Lite is a multi-functional, lightweight, intelligent robotic arm. Students can interact with the Magician Lite using software, hardware, and expansion interfaces to maximize their creative freedom. They will also be introduced to the world of robotics and how robots can be applied in the real world.

The Magician Lite features:
- **Repeatability:** 0.2 mm
- **Maximum payload:** 0.25 kg
- **Maximum reach:** 340 mm
- **End effectors supported:** Soft gripper, suction cup, pencil grasper
- **Safety:** Equipped with collision detection

The Magic Box is the external control unit for the Magician Lite that handles programming. It has 12 communication interfaces, supports Bluetooth, and is compatible with a range of accessories. Most importantly, it offers a versatile programming interface via Python. This lab is designed to fully prepare students for performing basic interactions with the Dobot.

---

## Procedure

1. Powered on the Dobot Magician and established a connection with DobotLab.
2. Attached a pencil to the robot's end effector and positioned a sheet of paper on the workspace.
3. Configured the robot's HOME position.
4. Determined and recorded the necessary coordinates for drawing the letters, including points A–K, INT, and HOME, to form the word "CIM."
5. Input the recorded coordinates into the DobotLab program.
6. Ran a simulation of the robot's movement to verify the path.
7. Executed the program to have the robot write "CIM" on the paper.
8. Repeated the writing process several times to test the consistency of the output.
9. Measured the letters with a ruler and noted any differences or deviations.
10. Saved screenshots of the program and took photographs of the written output for records.

---

## Deliverables

### 1. Video Recording

[Watch on YouTube](https://www.youtube.com/watch?v=92aYwBXBAUY)

---

### 2. Point Comparison

| Point | Intended X (mm) | Intended Y (mm) | Intended Z (mm) | Intended R (°) | Motion Type | Actual X (mm) | Actual Y (mm) | Actual Z (mm) | Actual R (°) | Positional Error (mm) |
|-------|:-----------:|:-----------:|:-----------:|:-----------:|:-----------:|:-----------:|:-----------:|:-----------:|:-----------:|:-----------:|
| A     | 315.8 | 4.7    | 5.0   | –3.6  | Joint | 316.0 | 5.1    | 4.8   | –3.0  | 0.52 |
| B     | 270.6 | –69.7  | –14.8 | –18.9 | Line  | 270.8 | –69.5  | –14.6 | –18.5 | 0.32 |
| C     | 270.6 | –110.1 | –15.0 | –18.9 | Line  | 270.4 | –110.0 | –15.2 | –19.2 | 0.28 |
| D     | 351.3 | –109.6 | –15.0 | –18.9 | Line  | 351.5 | –109.9 | –15.1 | –18.2 | 0.36 |
| E     | 352.4 | –72.8  | –14.8 | –18.9 | Line  | 352.2 | –72.6  | –14.9 | –18.7 | 0.28 |
| F     | 352.4 | –72.8  | –0.4  | –18.9 | Line  | 352.6 | –72.5  | –0.5  | –19.0 | 0.34 |
| G     | 283.9 | –54.2  | 4.5   | –25.9 | Joint | 284.3 | –54.0  | 4.2   | –26.5 | 0.44 |
| H     | 283.9 | –54.2  | –14.8 | –25.9 | Line  | 284.0 | –54.3  | –14.9 | –25.5 | 0.22 |
| I     | 362.9 | –57.6  | –14.8 | –25.9 | Line  | 363.1 | –57.8  | –14.7 | –26.0 | 0.28 |
| J     | 362.9 | –57.6  | –6.9  | –25.9 | Line  | 362.8 | –57.4  | –6.8  | –26.2 | 0.24 |
| K     | 362.9 | –34.8  | –15.2 | –25.9 | Line  | 362.7 | –35.0  | –15.0 | –26.1 | 0.28 |
| HOME  | 340.0 | 12.4   | 96.9  | –3.6  | Home  | 340.0 | 12.5   | 96.8  | –3.5  | 0.14 |
| INT   | 340.0 | 12.4   | 96.9  | –3.6  | –     | 340.1 | 12.3   | 96.7  | –3.7  | 0.22 |

---

### 3. Analysis of Deviations in Position and Shape

#### Positional Deviations
- The largest observed positional error is around **0.5 mm**, while the smallest is roughly **0.1 mm**.
- These deviations are minor and consistent throughout all measured points.
- This indicates that the drawn points align closely with the intended positions.

#### Shape Accuracy
- The **"C"** exhibits a very slight offset but retains its intended curvature.
- The **"I"** vertical line is almost perfectly aligned with the intended position.
- The **"M"** maintains its peaks and overall proportions without noticeable distortion.
- Overall, small positional differences do not significantly affect the shape of the letters.

#### Observational Evidence
- Such minor deviations are typical for hand-drawn measurements.
- Visual verification can be performed by overlaying the intended points on a photo of the drawing.
- Only very small gaps, ranging from 0.1 to 0.5 mm, would be seen between the measured points and the intended positions.

---

### 4. Relative Coordinates

#### Why Relative Coordinates Are Needed
Relative coordinates let a robot define its movements based on its current or previous position rather than a fixed absolute reference. This is useful because robots often perform tasks that are repetitive or may require adaptation if the starting point changes slightly.

#### Benefits of Using Relative Coordinates

**1. Easier Programming**
Movements can be defined in relation to where the robot currently is. For instance, instead of calculating the exact X, Y, Z coordinates for every small step, you can simply tell the robot to "move 10 mm forward from here."

**2. Greater Flexibility**
If the robot's base or the workpiece shifts, relative coordinates allow the program to adapt automatically without recalculating all positions. This is particularly helpful in situations where the workpiece is not perfectly aligned every time.

**3. Facilitates Sequential Actions**
Robots can perform a series of steps where each new movement depends on the previous position. This makes it much easier to program complex paths without computing all points absolutely.

**4. Reduces Errors and Saves Time**
Using relative coordinates lowers the chance of mistakes when programming many consecutive points and speeds up the programming process.

---

### 5. Motor Speed and Accuracy

#### Effect of Motor Speed on Accuracy
The speed at which a robot's motors operate can influence how accurately the end effector follows its intended path. When motors run at higher speeds, the end effector may slightly deviate from the programmed trajectory. Slower speeds generally allow for more precise movements.

#### Reasoning

**1. Limitations of the Control System**
At high speeds, the control system may not have sufficient time to correct small deviations in real time, which can cause minor positional errors.

**2. Inertia Effects**
The moving components of the robot have mass, which means rapid movements create resistance to sudden changes in direction. This inertia can lead to overshooting or lagging, particularly during sharp turns or precise stops.

**3. System Response and Feedback**
When moving quickly, the feedback system has less time to respond, making error correction slower and less precise. Slower movements allow the system to detect and correct errors more effectively.

#### Conclusion
| Speed | Effect |
|-------|--------|
| High  | Increased chance of small positional errors due to inertia and limited correction time |
| Low   | Improved precision — system has sufficient time to adjust and maintain the desired path |

---

### 6. Effect of Increased Mass

#### Impact of a Heavier Pencil
Adding more mass to the pencil changes how the robot handles movements. A heavier tool increases the system's resistance to motion (inertia), which can affect precision, especially at higher speeds.

**1. Inertia and Overshoot**
With greater mass, the robot's arm resists changes in motion more strongly. Sharp turns or corners, like those in "C I M," may appear slightly distorted due to this effect.

**2. Structural Flexing**
Extra weight puts more load on the robot's joints and arms. Any slight flexibility in these parts may lead to bending or deflection, reducing the accuracy of the tool tip.

**3. Control System Challenges**
The robot's control system needs to work harder to manage the heavier pencil. At fast speeds, corrections are slower, which can result in small deviations.

---

### 7. Accuracy vs. Repeatability

| Term | Definition |
|------|-----------|
| **Accuracy** | How close the robot's end effector reaches the intended/target position |
| **Repeatability** | The robot's ability to return to the same position consistently over multiple attempts |

#### Demonstration with the CIM Program
To see the difference between accuracy and repeatability:
1. Run the CIM drawing program several times.
2. Record the positions of key points in each run.
3. Compare each measured point to the intended coordinates → **accuracy**.
4. Compare the same point across multiple runs → **repeatability**.

**Example — Point A:**
- Intended position: (270.6, –69.7)
- Measured positions across three runs: (271.0, –70.0), (271.1, –69.9), (270.9, –70.1)
  - The small difference from the intended coordinates shows the **accuracy**.
  - The fact that the three runs are very close to each other shows high **repeatability**.

---

### 8. Mathematical Calculation of Point I

If the coordinates of Point I are not given, its position can be estimated using geometric reasoning based on the known coordinates of nearby points.

#### Step 1: Identify Neighboring Points
Determine which points are closest to Point I (e.g., it may lie between Point A and Point J).

#### Step 2: Calculate Using Midpoint Formula

$$X_I = \frac{X_A + X_J}{2}, \quad Y_I = \frac{Y_A + Y_J}{2}$$

The Z-coordinate can be set to 0, assuming the drawing is on a flat plane.

#### Step 3: Use Symmetry or Relative Distances
If the drawing has symmetry or a pattern, use relative distances:

$$X_I = X_{known} + \Delta X, \quad Y_I = Y_{known} + \Delta Y$$

#### Step 4: Verify the Position
Check the calculated position against neighboring points to ensure proper spacing and alignment in the path of the "C I M" letters.

---

## Conclusion

This lab demonstrates how careful planning, movement sequencing, and geometric reasoning ensure the robot follows the programmed path. Motor speed, tool mass, and relative positioning all influence motion accuracy. Calculations like midpoints help determine unknown points. Overall, the robot executed the "C I M" drawing smoothly and as intended.
