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

### 3. Mounting to a Shoe
For non-destructive testing:
*   **Adhesive:** Contact cement (e.g., Barge) allows for a strong bond that can be peeled off later.
*   **Straps:** Design small loops into the rigid frame to attach elastic bands or Velcro straps around the existing shoe.

---

## FreeCAD Parameter List for Prototyping

This list contains key variables for building a parametric CAD model in FreeCAD's Spreadsheet Workbench. This allows for rapid design changes by modifying a single source of truth.

```text
| Alias (Variabelnamn)      | Värde | Enhet | Beskrivning                                                              |
|---------------------------|-------|-------|--------------------------------------------------------------------------|
| `pCellDiameter`           | 12    | mm    | Ytterdiametern på en enskild, flexibel TPU-actuator-pod.                   |
| `pCellDepth`              | 4     | mm    | Totala djupet/höjden på TPU-podden.                                        |
| `pTargetStroke`           | 2     | mm    | Målsatt utskjutningslängd för dubben vid aktivering.                       |
| `pFrameWall`              | 1.5   | mm    | Väggtjockleken på den styva honeycomb-ramen (PET-G/ASA).                   |
| `pPodWall`                | 1.0   | mm    | Väggtjockleken på den flexibla TPU-podden.                                 |
| `pInsulationLayer`        | 1.0   | mm    | Tjockleken på värmeisoleringsskiktet mot foten.                            |
| `pTackHeadDiameter`       | 10    | mm    | Diametern på huvudet av häftstiftet som används som "anvil".               |
| `pTackHeadThickness`      | 0.5   | mm    | Uppskattad tjocklek på metallen i häftstiftets huvud.                      |
| `pTackNeedleLength`       | 3.5   | mm    | Den förkortade längden på häftstiftets nål (dubben).                       |
| `pSeptumDiameter`         | 3     | mm    | Diametern på den självläkande injektionsporten (septum).                    |
| `pSeptumHeight`           | 4     | mm    | Höjden på injektionsporten (samma som `pCellDepth`).                       |
| `pClearance`              | 0.2   | mm    | Generellt spel mellan den styva ramen och TPU-podden för enkel montering. |
```

### How to use in FreeCAD:
1. Open the `Spreadsheet Workbench`.
2. Create a new spreadsheet.
3. In Column A, write the alias name (e.g., `pCellDiameter`).
4. In Column B, write the value (e.g., `12`).
5. Right-click the cell in **Column B** and select `Properties -> Alias`. Enter the alias name from Column A.
6. In your sketches, when setting a dimension, click the `ƒx` icon and write `Spreadsheet.AliasName` (e.g., `Spreadsheet.pCellDiameter`).