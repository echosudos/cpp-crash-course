To ensure that LaTeX equations display properly on GitHub, you should use GitHub's support for rendering math expressions using the [GitHub Flavored Markdown (GFM)](https://github.blog/changelog/2022-09-15-latex-support-in-markdown/) syntax.

Here's how to do it:

- **Inline Math**: Wrap your LaTeX code with single dollar signs `$...$`.
- **Display Math**: Wrap your LaTeX code with double dollar signs `$$...$$`.

By formatting your equations this way, GitHub will render them correctly, including integral symbols and other mathematical notations.

Below is the cheatsheet formatted for GitHub with proper markdown and LaTeX syntax:

---

# **Circuit Analysis Cheat Sheet**

---

## 1. Thevenin's Theorem Guidelines

**Purpose:** Simplify a complex circuit to a single voltage source (`Vₜₕ`) in series with a resistor (`Rₜₕ`) across two terminals.

### With Independent Sources

1. **Remove the Load Resistor**: Disconnect the component between the two terminals of interest.
2. **Find** $V_{\text{th}}$ **(Thevenin Voltage)**:
   - Calculate the open-circuit voltage across the terminals.
3. **Find** $R_{\text{th}}$ **(Thevenin Resistance)**:
   - **Deactivate All Independent Sources**:
     - Replace **voltage sources** with short circuits.
     - Replace **current sources** with open circuits.
   - Calculate the equivalent resistance seen from the terminals.
4. **Draw The Thevenin Equivalent Circuit**:
   - A voltage source $V_{\text{th}}$ in series with a resistor $R_{\text{th}}$.

### Without Independent Sources (Dependent Sources Only)

1. **Remove the Load Resistor**.
2. **Apply a Test Source**:
   - Apply a known voltage ($V_{\text{test}}$) and calculate the resulting current ($I_{\text{test}}$), or vice versa.
3. **Calculate** $R_{\text{th}}$:
   - Use Ohm's Law: $R_{\text{th}} = \dfrac{V_{\text{test}}}{I_{\text{test}}}$.
4. **Note**: $V_{\text{th}}$ is zero when only dependent sources are present.
5. **Draw The Thevenin Equivalent Circuit**:
   - A resistor $R_{\text{th}}$ in series with the load.

---

## 2. Norton's Theorem Guidelines

**Purpose:** Simplify a complex circuit to a single current source ($I_N$) in parallel with a resistor ($R_N$) across two terminals.

### With Independent Sources

1. **Remove the Load Resistor**.
2. **Find** $I_{\text{N}}$ **(Norton Current)**:
   - Calculate the short-circuit current across the terminals.
3. **Find** $R_{\text{N}}$ **(Norton Resistance)**:
   - **Deactivate All Independent Sources**:
     - Replace **voltage sources** with short circuits.
     - Replace **current sources** with open circuits.
   - Calculate the equivalent resistance seen from the terminals.
4. **Draw The Norton Equivalent Circuit**:
   - A current source $I_{\text{N}}$ in parallel with a resistor $R_{\text{N}}$.

### Without Independent Sources (Dependent Sources Only)

1. **Remove the Load Resistor**.
2. **Apply a Test Source**:
   - Apply a known voltage ($V_{\text{test}}$) and calculate the resulting current ($I_{\text{test}}$), or vice versa.
3. **Calculate** $R_{\text{N}}$:
   - Use Ohm's Law: $R_{\text{N}} = \dfrac{V_{\text{test}}}{I_{\text{test}}}$.
4. **Note**: $I_{\text{N}}$ is zero when only dependent sources are present.
5. **Draw The Norton Equivalent Circuit**:
   - A resistor $R_{\text{N}}$ in parallel with the load.

---

## 3. Capacitor Formulas and Properties

### Basic Formulas

- **Charge-Voltage Relationship**:
  \[
  Q = C \times V
  \]
  Where:
  - $C$ = Capacitance (Farads)
  - $Q$ = Charge (Coulombs)
  - $V$ = Voltage (Volts)

- **Current-Voltage Relationship**:
  \[
  I(t) = C \times \frac{dV(t)}{dt}
  \]
  - **Derivative Form**: Shows how current depends on the rate of voltage change.

- **Voltage-Current Relationship**:
  \[
  V(t) = \frac{1}{C} \int I(t) \, dt + V_0
  \]
  Where:
  - $V_0$ = Initial voltage across the capacitor.

### Properties

- **Voltage Cannot Change Abruptly**:
  - A sudden change in voltage requires infinite current, which is not possible.

- **Simplification in Circuits**:
  - **At DC Steady State**:
    - Capacitors act as **open circuits** (no current flows through them).
  - **At High Frequencies**:
    - Capacitors act as **short circuits** (impedance decreases with frequency).

---

## 4. Inductor Formulas and Properties

### Basic Formulas

- **Voltage-Current Relationship**:
  \[
  V(t) = L \times \frac{dI(t)}{dt}
  \]
  Where:
  - $L$ = Inductance (Henrys)
  - $I(t)$ = Current (Amperes)

- **Current-Voltage Relationship**:
  \[
  I(t) = \frac{1}{L} \int V(t) \, dt + I_0
  \]
  Where:
  - $I_0$ = Initial current through the inductor.

### Properties

- **Current Cannot Change Abruptly**:
  - A sudden change in current requires infinite voltage, which is not possible.

- **Simplification in Circuits**:
  - **At DC Steady State**:
    - Inductors act as **short circuits** (they allow constant current flow).
  - **At High Frequencies**:
    - Inductors act as **open circuits** (impedance increases with frequency).

---

## 5. Mesh Analysis Guidelines

**Purpose:** Solve for unknown currents in planar circuits using loop equations.

### Steps

1. **Identify All Meshes**:
   - A mesh is a loop that does not enclose any other loops.

2. **Assign Mesh Currents**:
   - Typically assigned in the clockwise direction.

3. **Apply Kirchhoff’s Voltage Law (KVL) to Each Mesh**:
   - The sum of voltage drops equals zero around each loop.

4. **Write Equations**:
   - Account for shared components between meshes.

5. **Solve the System of Equations**:
   - Use algebraic methods or matrix techniques.

---

## 6. Basic/Ideal BJT Equations and Solving Guidelines

### Key Equations

- **Collector Current**:
  \[
  I_C = \beta \times I_B
  \]
  Where:
  - $\beta$ = Current gain (common-emitter configuration).

- **Emitter Current**:
  \[
  I_E = I_B + I_C
  \]

- **Voltage Relationships**:
  - **Forward-Active Mode**:
    - $V_{BE} \approx 0.7\,\text{V}$ (for silicon BJTs).
    - $V_{CE} > V_{BE}$.

### Solving Guidelines

1. **Assume Operating Region**:
   - Typically start with the transistor in the **active region**.

2. **Apply KVL and KCL**:
   - Use Kirchhoff's laws around loops and at nodes involving the BJT.

3. **Use BJT Relationships**:
   - Relate currents using $I_C = \beta \times I_B$ and $I_E = I_B + I_C$.

4. **Verify Assumptions**:
   - Ensure calculated voltages and currents are consistent with the assumed operating region.

---

## 7. Basic/Ideal MOSFET Equations and Solving Guidelines

### Key Equations for N-Channel Enhancement MOSFET

- **Threshold Voltage**:
  - $V_{\text{TH}}$ (Given in the datasheet).

- **Operating Regions**:
  - **Cutoff**:
    - $V_{GS} < V_{\text{TH}}$.
  - **Triode (Linear)**:
    - $V_{GS} > V_{\text{TH}}$ and $V_{DS} < V_{GS} - V_{\text{TH}}$.
  - **Saturation**:
    - $V_{GS} > V_{\text{TH}}$ and $V_{DS} \geq V_{GS} - V_{\text{TH}}$.

- **Drain Current**:

  - **Saturation**:
    \[
    I_D = \dfrac{1}{2} k_n (V_{GS} - V_{\text{TH}})^2
    \]
  - **Triode**:
    \[
    I_D = k_n \left[ (V_{GS} - V_{\text{TH}}) V_{DS} - \dfrac{V_{DS}^2}{2} \right]
    \]
  Where:
  - $k_n$ = Process transconductance parameter.

### Solving Guidelines

1. **Assume Operating Region**:
   - Start by assuming the MOSFET is in the **saturation region**.

2. **Apply Circuit Laws**:
   - Use KVL and KCL to find voltages ($V_{GS}$, $V_{DS}$) and currents ($I_D$).

3. **Use MOSFET Equations**:
   - Apply the appropriate equation based on the assumed region.

4. **Verify Assumptions**:
   - Check if $V_{GS}$ and $V_{DS}$ satisfy the conditions for the operating region.

5. **Iterate if Necessary**:
   - If assumptions are invalid, reassess and use the correct operating region.

---

## 8. Basic/Ideal Op-Amp Equations and Solving Guidelines

### Ideal Op-Amp Characteristics

- **Infinite Open-Loop Gain** ($A \rightarrow \infty$).
- **Infinite Input Impedance** ($R_{\text{in}} \rightarrow \infty$).
- **Zero Output Impedance** ($R_{\text{out}} = 0$).
- **Inputs Draw No Current**:
  - $I_+ = I_- = 0$.

### Golden Rules

1. **Voltage Equality at Inputs**:
   - $V_+ = V_-$ (due to infinite gain, any difference is amplified infinitely).

2. **No Input Current**:
   - Inputs draw negligible current ($I_+ = I_- = 0$).

### Common Configurations

- **Inverting Amplifier**:

  - **Gain**:
    \[
    A_v = -\left( \dfrac{R_f}{R_{\text{in}}} \right)
    \]
  - **Output Voltage**:
    \[
    V_{\text{out}} = -\left( \dfrac{R_f}{R_{\text{in}}} \right) V_{\text{in}}
    \]

- **Non-Inverting Amplifier**:

  - **Gain**:
    \[
    A_v = 1 + \left( \dfrac{R_f}{R_{\text{in}}} \right)
    \]
  - **Output Voltage**:
    \[
    V_{\text{out}} = \left[ 1 + \left( \dfrac{R_f}{R_{\text{in}}} \right) \right] V_{\text{in}}
    \]

- **Voltage Follower**:

  - **Gain**:
    \[
    A_v = 1
    \]
  - **Output Voltage**:
    \[
    V_{\text{out}} = V_{\text{in}}
    \]

### Solving Guidelines

1. **Identify the Configuration**:
   - Determine if the op-amp is in an inverting, non-inverting, or other configuration.

2. **Apply the Golden Rules**:
   - Use $V_+ = V_-$ and $I_+ = I_- = 0$.

3. **Write Node Equations**:
   - Use KCL at the inputs and outputs as needed.

4. **Solve for the Desired Variable**:
   - Find $V_{\text{out}}$, $V_{\text{in}}$, or other variables as required.

5. **Check Output Limits**:
   - Ensure that $V_{\text{out}}$ is within the supply voltage limits of the op-amp.

---

**Note:** This cheat sheet provides fundamental guidelines and formulas for basic circuit analysis. Always double-check your work and verify that all assumptions hold true for your specific circuit.

---

**Additional Tips:**

- Ensure you're viewing the markdown file directly on GitHub or in a markdown editor that supports GitHub Flavored Markdown with LaTeX rendering.
- If you have images or complex diagrams, consider using image links or embedding them using the `![Alt Text](image_url)` syntax.
- For the best rendering experience, make sure your equations are properly formatted and that all LaTeX commands are correct.

Let me know if you need any further assistance!