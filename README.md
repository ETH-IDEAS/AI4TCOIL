# AI4TCOIL

AI4TCOIL is an ETH IDEAS research codebase for **AI-assisted T-coil synthesis and modeling**, centered on the notebook:

- `TCoil_Dataset_Generator_and_Training.ipynb`

The goal is to **accelerate the design loop** for broadband high-frequency wireline front-end applications by replacing slow, repeated EM evaluations with a fast ML surrogate, then using lightweight optimization to propose candidate geometries that meet target specs.

> Note: This repository does **not** include any proprietary PDK, foundry collateral, or restricted EM libraries. If your workflow depends on a specific PDK, you must supply it locally under your own license.

---

## What is inside

### Core workflow
1. **Dataset generation**
   - Sample T-coil geometry parameters (layout level or parameterized macro level).
   - Run EM (or a precomputed EM dataset) to obtain responses (e.g., S-parameters and bandwidth metrics).
2. **ML surrogate training**
   - Train a regression model that maps **geometry → EM response / metrics**.
   - This reduces evaluation latency from EM runtime to near-instant inference.
3. **Inverse design / synthesis**
   - Use an optimization loop (currently random search style) to propose geometries that satisfy target constraints.
   - Export candidates for EM verification and downstream integration.

### Why this matters
In practical design flows, passive components like T-coils can become an iteration bottleneck due to EM-driven tuning. This repo demonstrates a path to reduce that bottleneck by combining:
- **ML-assisted EM prediction**
- **Optimization-driven geometry proposal**
- **Verification with EM, then integration into circuit level evaluation**

### Environment
Recommended: Python 3.10+ with Jupyter. Refer to the instructions in the notebook.
