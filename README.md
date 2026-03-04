# GlazeGuard - Adaptive Open Source Traction
An intelligent, passive footwear system designed to prevent slip-and-fall injuries.

## Background
Inspired by a personal spinal injury, this project aims to create a universal, 
low-cost safety mechanism that remains accessible to all through Open Source.

## License
This project is licensed under the **CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN-OHL-S v2)**.

Our goal is to establish "Prior Art" and ensure this life-saving technology remains accessible to all, preventing restrictive patenting. By using a strong reciprocal license, we ensure that any improvements or modifications to the design also remain open and available to the community.

You can find the full license text in the `LICENSE` file in the root of this repository.

## Project Documentation
Dive deeper into the engineering behind GlazeGuard:

*   **Theory of Operation:** Detailed physics, Euler buckling formulas, and the Nanocellulose ice composite.
*   **Bill of Materials (BOM):** Parts list for building a prototype.
*   **Manufacturing Guide:** How to 3D print and assemble the cells.
*   **Design Variants:** Alternative designs like the "Cold-Finger" and "Pumpkin Seed" drive.
*   **Contributing:** How you can help (FEA analysis, CAD, etc.).
*   **Roadmap / TODO:** Current status and next steps.

## Simple illustration of concept
```text
STAGE 1: WARM (>0°C)      STAGE 2: COLD (ICE)       STAGE 3: COLD (HARD FLOOR)
      [ Rubber ]                [ Rubber ]                [ Rubber ]
      |        |                |        |                |        |
      | [H2O]  |  <--Liquid     | [ICE]  |  <--Solid      | [ICE]  |
      |__----__|                |__-^^-__|                |__-^^-__|
         |  |                      |  |                      /  /   <-- Buckling!
         |  |                      |  |                     /  /
         [__]   <-- Retracted      [__]   <-- Deployed     [__]     <-- Recessed
      ----------                --/----\--                ----------
      (Asphalt)                    (Ice)                  (Hard Floor)
```

Panel 1: "WARM STATE" (>0°C)

    Visual: Cross-section of the capsule embedded in a rubber sole (grey). The water reservoir at the bottom is highlighted in blue.

    Mechanics: The water is liquid. The bistable membrane is in its "lower," concave position. The traction stud (dark grey) is fully retracted into the sole.

    Label (TL;DR): "System Disarmed. Water is liquid. Stud is retracted."

Panel 2: "FROZEN STATE - ICE" (<0°C)

    Visual: The same capsule, but the water reservoir is now highlighted in light blue/white to indicate ice. An arrow indicates the expansion (9%).

    Mechanics: The ice has forced the membrane to "pop" up into its convex position. The traction stud is deployed and penetrates a stylized ice sheet.

    Label (TL;DR): "System Armed. Ice expands, deploying the stud. High penetration force."

Panel 3: "FROZEN STATE - INDOOR HARD FLOOR" (<0°C)

    Visual: The capsule is still frozen, but it is now resting against a hard surface (e.g., tile).

    Mechanics: Upward pressure has caused the conical buckling axis (yellow arrows) to flex elastically. The stud is retracted flush with the surface of the sole.

    Label (TL;DR): "Safe Transition. Stud buckles elastically on hard surfaces. No skating effect."

Technical Labels
In all three panels, leader lines point to the following components:

    Tungsten Carbide Tip (The stud)

    Progressive Buckling Column (The adaptive axis)

    Bistable Snap-Action Diaphragm (The membrane)

    Distilled Water (Phase-Change Medium) (The water)

    TPU Encapsulation (The capsule)