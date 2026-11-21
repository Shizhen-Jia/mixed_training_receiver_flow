# Mixed Training Receiver Flow

**Two-branch interference cancellation with a modular FPGA/PS architecture.**

This project studies two complex receiver records containing copies of the same unknown interferer plus independent noise. It estimates their relative delay and Doppler, aligns them, learns noise-normalized weights, and combines the branches to suppress the common interference.

**Contributor:** SJ00425 (individual project)\
**Current stage:** Initial planning. There is no implemented HLS/RTL kernel, bitstream, board demonstration, or measured performance result in this repository yet.

## Initial plan

The course submission document is **[plans/initial_plan.md](plans/initial_plan.md)**. It contains the project team, mathematical IP definition, acceleration rationale, architecture alternatives, selected PS/PL partition, explicit interfaces, and verification milestones.

Once this repository is public on GitHub, submit the URL of that file on the `main` branch. See [the submission guide](SUBMISSION.md) for the remaining steps.

## Selected design

| Module | Purpose | Initial execution location |
|---|---|---|
| M01 | FFT coarse delay-Doppler search | PS |
| M02 | Bounded gradient and matched final refinement | PS |
| M03 | Doppler derotation, integer delay, fractional-delay FIR | PL |
| M04 | Covariance accumulation and noise normalization | PL reductions; PS normalization |
| M05 | Minimum-eigenvector weight solve | PS |
| M06 | Two-branch weighted cancellation | PL |

The first hardware target is capture/replay using shared DDR, DMA, AXI4-Stream IQ transport, bounded internal FIFOs, and AXI4-Lite configuration/status. The PS controls training and independent testing. The exact board/part, numeric formats, and implementation schedule will be selected and validated during development.

Here, “training” means learning alignment and covariance from received observations. The experiment contains **interference and noise only**; it does not include desired-signal recovery, known training symbols, or payload decoding.

## Repository contents

```text
mixed_training_receiver_flow/
├── README.md                          # Current scope and implementation status
├── plans/
│   └── initial_plan.md                # Graded initial-plan submission
├── mixed_training_receiver_flow.md    # Expanded research/development plan
├── assets/receiver_flow/
│   ├── m02_gradient_candidate_loop.png
│   └── m02_gradient_candidate_loop.svg
├── references.md                      # Manuscript and documentation sources
├── SUBMISSION.md                      # GitHub / grading / submission steps
├── .gitattributes
└── .gitignore
```

The expanded plan describes proposed modules and acceptance criteria; it is not evidence that those modules have been built. The initial plan selects a manageable first partition from that broader design.

## Development and validation

1. Build the floating-point six-module reference and save intermediate vectors.
2. Bring up data transport and the weighted combiner with host-loaded weights.
3. Implement and verify delay/Doppler alignment and covariance reductions.
4. Integrate PS weight learning, atomic configuration updates, and independent test replay.
5. Compare fixed-point/C/RTL outputs and measure FPGA timing, resources, and throughput.

The future validation suite will cover signed and fractional offsets, unequal noise, independent-test residual INR, numerical failure cases, backpressure, and reset. There are currently no build or test commands because implementation has not started. Generated tool projects, temporary captures, credentials, and submission archives are excluded by `.gitignore`; curated test vectors and result summaries should be committed when available.

## Sources

See [references.md](references.md) for the supplied manuscript and official course/AMD documentation. The local manuscript PDF and the course repository are not bundled into this repository. No license has been selected for this project yet.
