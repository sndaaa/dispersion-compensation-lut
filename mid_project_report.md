# Configurable FNT Dispersion-Compensation Intermediate Project Report

- RTL chain: serial input → serial-to-parallel conversion → FNT → configurable compensation LUT → IFNT → parallel-to-serial conversion.
- UART packet format: A5, address_hi, address_lo, data_low, data_high; FF/FE selects the transform length, and FF/FD controls bypass.
- Verified transform lengths: 16, 64, and 256; one dispersed block for each length plus one 16-point bypass block.
- Result: every output symbol matches the Python reference, with a maximum error of 0.

| N | Time-multiplexed cycles/block | Theoretical symbol rate at 100 MHz | Theoretical block latency |
|---:|---:|---:|---:|
| 16 | 548 | 2.9197 Msym/s | 5.480 μs |
| 64 | 8324 | 0.7689 Msym/s | 83.240 μs |
| 256 | 131588 | 0.1945 Msym/s | 1315.880 μs |

The generic core time-multiplexes one modular multiplier, making it suitable for learning and resource-constrained designs. fnt16_pipeline.v remains a fully unrolled, high-throughput 16-point option. Final resources and frequency must be confirmed with the target FPGA synthesis tool.

## Python Reference Timing (Method Demonstration Only)
- N=16: 0.000090 s/block (pure Python reference implementation)
- N=64: 0.001536 s/block (pure Python reference implementation)
- N=256: 0.032402 s/block (pure Python reference implementation)
