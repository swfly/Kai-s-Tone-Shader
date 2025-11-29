# Kai's Tone Shader

A JSFX (Reaper) library that explores a **non-skeuomorphic** approach to guitar tone.

Instead of simulating physical circuits (capacitors, tubes, voltage), this project builds tone using pure mathematical functions and signal processing concepts. I call this "Tone Shading"—similar to how graphics shaders calculate color, I calculate sound.

## Philosophy

Most amp sims try to replicate 50-year-old hardware, limiting you to the flaws and interfaces of the past.

Here, I deconstruct the guitar amp into its mathematical functions rather than simulating physical components:
1.  **Distortion is Waveshaping:** I use kernels (`tanh`, `sigmoid`) and Chebyshev polynomials to shape harmonics, not tube simulations.
2.  **Tone Stack is EQ:** I use precise digital Biquad filters, avoiding the messy interaction of passive analog circuits.
3.  **Cabinet is Convolution:** I use procedural Impulse Responses and envelope followers to shape the frequency and dynamics.

## Audio Demo

A comparison to verify that this approach produces a usable tone (it doesn't have to be "better" here).

| Sample | Description | Playback |
| :--- | :--- | :--- |
| **Riff 1 (A)** | Modern High Gain | <audio controls src="https://swfly.github.io/Kai-s-Tone-Shader/sample/riff1_A.mp3"><a href="https://swfly.github.io/Kai-s-Tone-Shader/sample/riff1_A.mp3">▶️ Listen (Source A)</a></audio> |
| **Riff 1 (B)** | Modern High Gain | <audio controls src="https://swfly.github.io/Kai-s-Tone-Shader/sample/riff1_B.mp3"><a href="https://swfly.github.io/Kai-s-Tone-Shader/sample/riff1_B.mp3">▶️ Listen (Source B)</a></audio> |

<details>
<summary><strong>🔍 Click to reveal sources</strong></summary>

* **A:** Logic Pro's Amp Designer, "Modern British Stack" (Circuit Emulation)
* **B:** **Kai's Tone Shader** (Functional "Shading")
</details>

## Structure

The DSP is split into three modules:

1.  **Core (Preamp):** Handles waveshaping and harmonic distortion.
2.  **Tone Stack (EQ):** A flexible 3-Band EQ.
3.  **Output (Power Amp/Cab):** Handles physically-inspired EQ and final time-domain smearing (procedural IR).

## How to Use

1.  Download this repository.
2.  Open **Reaper**.
3.  Create a new JSFX plugin and paste the code from the `effects` folder.
