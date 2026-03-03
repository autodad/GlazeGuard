# Design Variants: Addressing Thermal Lag

To ensure the system reacts quickly to icy conditions, we are exploring two alternative geometries to minimize thermal resistance ($R_{th}$).

## Variant A: The "Pumpkin Seed" Drive (Annular Surface-Actuation)
*Goal: Move the water as close to the ground as possible.*

In this design, the water is not stored in a deep chamber, but in a **Toroidal Ring (Donut shape)** surrounding the stud, located almost flush with the tread surface.

### Mechanism: Radial-to-Axial Conversion
Instead of pushing a membrane from behind, this method uses the "Pumpkin Seed Effect" (squeezing a tapered object to eject it).

1.  **Geometry:** The stud shaft is **Tapered** (Conical), being wider at the bottom (ground side) and narrower at the top.
2.  **The Water Ring:** A hollow ring of water surrounds this tapered shaft.
3.  **Actuation:**
    *   The outer wall of the ring is rigid rubber (the sole).
    *   When the water freezes, it expands. Since it cannot expand outwards, it expands **Inwards** (radially).
    *   This constricting ice ring squeezes the tapered shaft.
    *   Due to the slope of the taper, this radial "squeeze" is converted into a powerful **Axial Force**, shooting the stud downwards into the ice.

**Pros:**
*   **Instant Reaction:** The water is separated from the ice by only a thin layer of TPU (0.5mm).
*   **High Force:** The mechanical advantage of the wedge shape multiplies the expansion force.

**Cons:**
*   **Sealing:** Requires a dynamic seal around the moving stud at the surface, which is prone to dirt ingress.

---

## Variant B: The "Cold-Finger" (Integrated Thermal Bridge)
*Goal: Use the stud itself as a thermal probe.*

Rubber is a thermal insulator ($0.15 W/mK$), but Tungsten Carbide is a conductor ($110 W/mK$). This variant keeps the water safely deep inside the sole but uses the stud to transport the "cold" to the water.

### Mechanism: Internal Freezing
1.  **Geometry:** The stud is not just a tip; it has a long tail (shank) that extends backwards, penetrating through the membrane and **into the water reservoir**.
2.  **Sealing:** A flexible O-ring or bonded diaphragm seals the shank where it enters the water chamber.
3.  **Actuation:**
    *   When the user steps on ice (-5°C), the exposed Tungsten tip instantly drops in temperature.
    *   The "Cold" travels up the metal shank into the water reservoir in milliseconds.
    *   The water freezes **from the inside out** (nucleating on the metal shank).
    *   As the ice forms around the shank, it expands and pushes against the bistable mechanism as described in the original theory.

**Pros:**
*   **Durability:** The fragile water chamber remains protected deep inside the sole.
*   **Speed:** Thermal conductivity of metal ensures near-instant reaction without exposing the water.

**Cons:**
*   **Complexity:** Requires a reliable seal where the moving shank enters the water chamber.

---

## Recommendation
We recommend prototyping **Variant B (Cold-Finger)** first. It offers the best balance of durability and reaction speed.

*   **Why?** Placing a water bladder (Variant A) directly on the tread surface exposes it to puncture risks from glass, sharp rocks, and abrasion. Using the stud as a "Heat Pipe" is a solid-state engineering solution that solves the thermal lag without compromising structural integrity.