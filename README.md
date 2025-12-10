# GROMACS 2025.4 Prebuilt (Windows, CUDA GPU Support)

This repository provides a **precompiled Windows binary** of [GROMACS 2025.4](https://www.gromacs.org/) with **CUDA GPU acceleration**. This build is intended for users who want to run GROMACS on Windows with NVIDIA GPUs, without the need to compile from source.

## ✅ Features

- **Version:** GROMACS 2025.4
- **OS:** Windows 64-bit
- **GPU Acceleration:** CUDA 13.0
- **Compatible GPU Architectures:**

  | CUDA Architecture | Code Name       | Example GPU                        |
  |-------------------|-----------------|------------------------------------|
  | `sm_75`           | Turing          | RTX 2080 Ti, RTX 2060              |
  | `sm_80`           | Ampere          | A100, RTX 3080, RTX 3090           |
  | `sm_86`           | Ampere          | RTX 3060, RTX 3070 Ti              |
  | `sm_89`           | Ada Lovelace    | RTX 4090, RTX 4080                 |
  | `sm_90`           | Hopper          | H100, GH200                        |
  | `sm_100`          | Blackwell       | GB200, B200                        |
  | `sm_120`          | Blackwell       | RTX PRO Series, RTX 50** Series    |
  | `sm_121`          | Blackwell       | NVIDIA GB10 (DGX Spark)            |

- **Built using:**
  - Visual Studio 17 2022
  - Ninja 1.13.2
  - CUDA Toolkit 13.0
  - FFTW 3.3.5 (dll64)

## 📦 Download

Head over to the [**Releases**](https://github.com/Arifmaulanaazis/Gromacs-Prebuild-Windows/releases) section to download the latest prebuilt binaries.

> ⚠️ Make sure to download the correct archive for your system.

## 📁 Included Files

The prebuilt archive is organized as follows:

```
gmx/
├── GMXRC.bat                   # Environment loader for Windows
├── bin/
│   ├── gmx.exe                 # Main GROMACS executable
│   ├── cufft64_11.dll          # CUDA FFT runtime
│   ├── libfftw3f-3.dll         # FFTW runtime
│   └── [other helper files, scripts, and autocompletion files]
├── include/
│   └── gromacs/               # Header files for development
├── share/
│   └── gromacs/
│       ├── top/               # Force field and molecular data
│       └── README.tutor       # Tutorial and additional documentation
```

## ⚙️ Quick Start

1. **Extract** the downloaded archive to your desired location.
2. **Activate** the GROMACS environment:
   - Double-click `GMXRC.bat` from the `gmx` folder.
   - This script automatically adds the `bin/` directory to your session `PATH`.
3. **Test** the installation by opening a new Command Prompt and executing:
   ```bash
   gmx -v
   ```
   You should see version information along with details about CUDA and GPU support.

## 🚀 Running GROMACS with GPU Acceleration

After setting up the environment, you can run your simulations as usual. For example, to start a molecular dynamics run:

```bash
gmx mdrun -s topol.tpr
```

Or to verify GPU support, use:
```bash
gmx mdrun -v -nb gpu
```

Check the output for confirmation of CUDA support and active GPU acceleration.

## 📌 Additional Notes

- **Driver Requirements:** Ensure you have the latest NVIDIA drivers installed that are compatible with CUDA 12.1.
- **Environment Setup:** The `GMXRC.bat` file sets the necessary `PATH` for the current session. For permanent configuration, consider adding the `bin/` directory to your system `PATH`.

---

Made with ❤️ by Arif Maulana Azis
Contributions and feedback are welcome!
