# ST-FlowNet
The datasets of ST-FlowNet

📌 *The paper is currently under review. The datasets will be released as soon as the paper is accepted.*

## Single-condition Hydrofoil Dataset
- **naca0015_mach_0.003_aoa_10.0_re_1000_samples_1500.npz**: NACA0015 hydrofoil, with 1500 time steps, angle of attack 10°, Mach number 0.003, and Reynolds number 1000. The chord length of the hydrofoil is 1 meter.

## Single-condition Cylinder Dataset
- **cylinder_mach_0.003_aoa_0.0_re_200_samples_1500.npz**: Cylinder, with 1500 time steps, angle of attack 0°, Mach number 0.003, and Reynolds number 200. The diameter of the cylinder is 1 meter.

## Multi-condition Hydrofoil Dataset
- **train**: Contains 6 hydrofoils (`NACA0012`, `NACA0015`, `NACA2309`, `NACA2412`, `NACA4418`, `NACA4712`), 6 Reynolds numbers (from 1000 to 1500 with a step of 100), and 6 angles of attack (from 10° to 15° with a step of 1°), totaling 216 cases. 24 cases are randomly selected as the validation set.
- **val**: Contains 24 cases used for validation.
- **test**: Contains 4 hydrofoils (`NACA002`, `NACA2212`, `NACA2415`, `NACA4412`), with Reynolds numbers from 1000 to 1600 (step of 100) and angles of attack from 10° to 15° (step of 0.5°). For each hydrofoil, 6 pairs of Reynolds number and angle of attack (Re, AoA) are randomly selected, totaling 24 cases.

### Example: **train** folder
- **train.npy**: Contains flow field snapshots for all cases, with the shape `[num_cases, num_time_steps, channels, height, width]`, where `num_cases` is the number of cases, `num_time_steps` is the number of time steps, `channels` is the number of channels, `height` is the height of the snapshots, and `width` is the width of the snapshots.
- **train_loc.npy**: Contains grid positions for all cases, with the shape `[num_cases, 2, height, width]`. Here, `num_cases` is the number of cases, and `[2, height, width]` is the ($x$, $y$) coordinates for each pixel.
- **train_case_dict.npy**: A dictionary in the format `{0: 'nacaxxxx', 1: 'nacaxxxx', ...}`, mapping the case number to the corresponding hydrofoil name.
