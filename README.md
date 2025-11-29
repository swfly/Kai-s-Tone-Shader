# Kai's Tone Shader

A JSFX (Reaper) library that explores a **non-skeuomorphic** approach to guitar tone.

Instead of simulating physical circuits (capacitors, tubes, voltage), this project builds tone using pure mathematical functions and signal processing concepts. We call this "Tone Shading"—similar to how graphics shaders calculate color, we calculate sound.

## Philosophy

Most amp sims try to replicate 50-year-old hardware, limiting you to the flaws and interfaces of the past.

This project deconstructs the signal chain into its functional essence:
1.  **Distortion is Waveshaping** (Math functions, not tube simulations).
2.  **Cabinet is EQ** (Filters, not physical boxes).
3.  **Dynamics is Envelope Following** (Compression, not voltage sag).

## Audio Demo

A comparison to verify that this approach produces a usable tone (it doesn't have to be "better" here).

| Sample | Description | Link |
| :--- | :--- | :--- |
| **Riff 1 (A)** | Modern High Gain | [▶️ Listen to A](sample/riff1_A.mp3) |
| **Riff 1 (B)** | Modern High Gain | [▶️ Listen to B](sample/riff1_B.mp3) |

<details>
<summary><strong>🔍 Click to reveal sources</strong></summary>

* **A:** Logic Pro's Amp Designer, "Modern British Stack" (Circuit Emulation)
* **B:** **Kai's Tone Shader** (Functional "Shading")
</details>

## Structure

The DSP is split into three modules:

1.  **Core (Preamp):** Handles waveshaping and harmonic distortion. Uses `tanh` and polynomial functions to mimic saturation curves.
2.  **Tone Stack (EQ):** A flexible parametric EQ. It replaces the traditional interactive Bass/Mid/Treble circuit with precise frequency shaping.
3.  **Output (Power Amp/Cab):** Handles dynamics (compression/sag) and final frequency shaping (IR/Cab simulation).

## How to Use

1.  Download this repository.
2.  Open **Reaper**.
3.  Create a new JSFX plugin and paste the code from the `effects` folder.
