# Configurable Frequency-Domain Dispersion Compensation LUT

A configurable frequency-domain dispersion-compensation coefficient LUT with UART configuration registers and an FNT processing path.

## Contents

- configurable LUT and dispersion-apply modules
- sequential FNT core and top-level integration
- UART receiver, register file, and streaming configuration logic
- memory vectors, simulation logs, and verification results
- `paper_dispersion-compensation-lut_en.docx` — English design report

## Focus

Runtime coefficient configuration, fixed-point signal processing, RTL integration, and intermediate-result verification.

## Design report

[Read the English design report](./paper_dispersion-compensation-lut_en.docx)

## Reproduce verification

Python 3 and Icarus Verilog (iverilog and vvp on PATH). Install NumPy with `python -m pip install numpy`.

Run `python run_mid_project.py` from the repository root. The script regenerates simulation outputs using deterministic test vectors. It does not require files from the author's computer.

## Scope

These are educational RTL simulations. Passing simulation is not a claim of FPGA timing closure, board-level validation, or a physical fiber-channel model.
