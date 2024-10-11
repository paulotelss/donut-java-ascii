## Detailed Explanation of the Donut ASCII Algorithm

This project implements an algorithm that renders a rotating 3D donut using ASCII characters in Java. The main idea is to project a 3D shape onto a 2D plane and represent it using characters of varying brightness. The algorithm uses trigonometric functions to simulate the rotation and depth of the donut.

**Initialization:**
- The algorithm starts by initializing the rotation angles `A` and `B` to 0. These angles control the rotation of the donut along two axes.

**Buffers: Two buffers are used:**
- `z[]`: A depth buffer that stores the depth of each point on the donut.
- `b[]`: A character buffer that stores the corresponding ASCII character for each point.

**Main Loop:** The rendering happens inside an infinite loop, which continuously updates the donut's position and redraws it:

- The buffers are reset at the beginning of each loop iteration.
- Two nested loops iterate over the angular coordinates `j` (for the vertical angle) and `i` (for the horizontal angle) to calculate the position of each point on the donut in 3D space.

**3D to 2D Projection:**

- For each point on the donut, trigonometric functions (`sin` and `cos`) are used to calculate its 3D coordinates.
- These coordinates are then projected onto a 2D plane using perspective projection formulas. The projection takes into account the rotation angles `A` and `B`, which are incremented slightly in each loop iteration to create the animation effect.

**Character Selection:**
- The brightness of each point is determined by its angle relative to a light source.
- Based on this brightness, a character is selected from the string `".,-~:;=!*#$@"`, where each character represents a different level of brightness.

**Depth Buffering:**

- Before placing a character on the 2D plane, the algorithm checks if this point is closer to the viewer than any previously calculated point at the same position. This ensures that only the visible surface of the donut is drawn.

**Rendering:**

- Once all points are processed, the character buffer is printed to the console, creating a frame of the animation.
- The rotation angles `A` and `B` are then incremented to create the effect of continuous rotation.

**Frame Rate:** A small delay is added between frames using `Thread.sleep(30)` to control the animation speed.

## This implementation effectively demonstrates how trigonometry and buffer manipulation can be used to create a simple 3D rendering in a text-based environment.



<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=65&section=footer"/>
