# Prototyping Hacks & Community Challenges

This document is for accessible, low-cost methods to build and test core concepts of the GlazeGuard project. The goal is to allow anyone with basic maker tools (like a 3D printer) to contribute.

## The "Tack-in-Membrane" Cell (v0.2 Prototype Concept)

A key challenge is creating a durable, effective, and bistable actuator. This "hack" uses an off-the-shelf component—a thumbtack—to solve several problems at once. The thumbtack's head acts as a load-spreader or "anvil" inside a flexible, 3D-printed membrane.

### 1. The Component "Sandwich"

*   **The "Anvil" (Thumbtack):** A standard metal thumbtack. The broad, flat head acts as a piston to receive force from the expanding ice. The needle is clipped or shortened to the desired length (~3-4mm) to become the traction stud.
*   **The Membrane:** A 3D-printed TPU disc or a piece of heavy-duty silicone. The thumbtack's head is "overmolded" (by pausing the print and inserting it) or glued into a pocket in this membrane.
*   **The Bistability:** By printing the flexible membrane with a slight "dome" shape, we create a structure that wants to "snap" between a concave (retracted) and convex (deployed) state.

### 2. Why This Works for Early Prototypes

*   **Pressure Distribution:** When the NC-Ice expands, it pushes against the entire surface of the thumbtack head. This prevents the sharp point of a simple stud from just sinking back into the ice core or piercing the membrane.
*   **Simplicity & Accessibility:** It uses off-the-shelf components. Anyone with a 3D printer and a box of thumbtacks can build and test a core actuation cell.
*   **Durability:** The metal head protects the softer polymer membrane from being damaged by the repeated mechanical movement of the stud.

---

## Community Challenge

This "Thumbtack Hack" makes the project very accessible for community development. We are opening a bounty for a well-designed, printable test unit.

*   **GitHub Issue Title:** `[Bounty] Design a 3D-printable housing for a standard thumbtack-based PCPT cell.`
*   **Description:** `We need a .STL file for a test housing where a standard 10mm thumbtack can be inserted during the 3D print (using a pause-at-height command) or snapped/glued in post-print. The design should include a small reservoir and a rim for sealing.`

---

## 3D Printing Guide: Materials & Settings

To build a functional prototype that can be tested under a shoe, specific materials and settings are required to handle the mechanical loads.

### 1. The Rigid Honeycomb Frame
This component acts as the structural skeleton. It must be stiff enough to resist walking pressure but tough enough not to crack.

*   **Recommended Materials:**
    *   **PET-G:** Best for beginners. Easy to print, good layer adhesion, and slightly flexible (tough).
    *   **ASA:** Best for durability. UV-resistant and very rigid, but requires a controlled print environment (enclosure) to prevent warping.
*   **Print Settings:**
    *   **Perimeters (Walls):** 3-4 lines (approx. 1.2mm - 1.6mm). This is crucial for strength.
    *   **Infill:** 50-70% using a strong pattern like **Cubic** or **Gyroid**.
    *   **Top/Bottom Layers:** 4-5 layers to ensure a solid surface for gluing/mounting.

### 2. The Flexible Actuator Pods
These hold the water and the mechanism. They must be watertight and elastic.

*   **Recommended Material:** **TPU (Thermoplastic Polyurethane)**.
    *   **Hardness:** 95A is easier to print. 85A is softer and better for the buckling column but harder to print.
*   **Print Settings:**
    *   **Walls:** 2-3 perimeters.
    *   **Infill:** **100%** for the "Injection Port" (Septum) area. **0% (Hollow)** for the water chamber.
    *   **Speed:** Print slowly (15-30 mm/s) to ensure watertight layer bonding.

### 2.1. The "Slicer Hack" (Advanced Infill Strategy)
Instead of modeling a hollow chamber which requires difficult internal supports, you can model a solid block and use the Slicer to generate the internal structure.

*   **The Concept:** Use the Infill as the return spring.
*   **Recommended Pattern:** **Gyroid**.
    *   *Why?* Gyroid is fully permeable (fluid flows through it easily) and acts as an isotropic spring.
*   **Settings:**
    *   **Infill Density:** 10-15% (Creates volume for water while providing structural rebound).
    *   **Walls:** Thick (1.5mm+) to prevent bulging.
*   **The Injection Port (Septum):**
    *   Since the cell is mostly hollow, you must use a **Modifier Mesh** in your slicer (e.g., Cura "Per Model Settings").
    *   Place a small cylinder intersecting the wall.
    *   Set this modifier to **100% Infill**. This creates a solid rubber block to pierce with a needle for filling.

### 3. Mounting to a Shoe
For non-destructive testing:
*   **Adhesive:** Contact cement (e.g., Barge) allows for a strong bond that can be peeled off later.
*   **Straps:** Design small loops into the rigid frame to attach elastic bands or Velcro straps around the existing shoe.

---

## FreeCAD Parameter List for Prototyping

This list contains key variables for building a parametric CAD model in FreeCAD's Spreadsheet Workbench. This allows for rapid design changes by modifying a single source of truth.

```text
| Alias (Variable Name)     | Value | Unit  | Description                                                              |
|---------------------------|-------|-------|--------------------------------------------------------------------------|
| `pCellDiameter`           | 12    | mm    | Outer diameter of a single, flexible TPU actuator pod.                   |
| `pCellDepth`              | 4     | mm    | Total depth/height of the TPU pod.                                       |
| `pTargetStroke`           | 2     | mm    | Target stroke length for the stud upon activation.                       |
| `pFrameWall`              | 1.5   | mm    | Wall thickness of the rigid honeycomb frame (PET-G/ASA).                 |
| `pPodWall`                | 1.0   | mm    | Wall thickness of the flexible TPU pod.                                  |
| `pInsulationLayer`        | 1.0   | mm    | Thickness of the thermal insulation layer against the foot.              |
| `pTackHeadDiameter`       | 10    | mm    | Diameter of the thumbtack head used as the "anvil".                      |
| `pTackHeadThickness`      | 0.5   | mm    | Estimated thickness of the metal in the thumbtack head.                  |
| `pTackNeedleLength`       | 3.5   | mm    | The shortened length of the thumbtack needle (the stud).                 |
| `pSeptumDiameter`         | 3     | mm    | Diameter of the self-healing injection port (septum).                    |
| `pSeptumHeight`           | 4     | mm    | Height of the injection port (same as `pCellDepth`).                     |
| `pClearance`              | 0.2   | mm    | General clearance between the rigid frame and the TPU pod for easy assembly. |
```

### How to use in FreeCAD:
1. Open the `Spreadsheet Workbench`.
2. Create a new spreadsheet.
3. In Column A, write the alias name (e.g., `pCellDiameter`).
4. In Column B, write the value (e.g., `12`).
5. Right-click the cell in **Column B** and select `Properties -> Alias`. Enter the alias name from Column A.
6. In your sketches, when setting a dimension, click the `ƒx` icon and write `Spreadsheet.AliasName` (e.g., `Spreadsheet.pCellDiameter`).