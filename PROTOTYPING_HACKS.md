# Prototyping Hacks & Community Challenges

This document is for accessible, low-cost methods to build and test core concepts of the GlazeGuard project. The goal is to allow anyone with basic maker tools (like a 3D printer) to contribute.

## The "Tack-in-Membrane" Cell (V1.1 Prototype Concept)

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