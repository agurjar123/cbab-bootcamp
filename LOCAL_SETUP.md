# Local Setup Guide

How to run the CBAB bootcamp notebooks on your own computer.
Pick your operating system and follow the steps in order.

---

## Mac

### Step 1 — Install R

1. Go to **https://cran.r-project.org/bin/macosx/**
2. Download the `.pkg` file for your chip:
   - **Apple Silicon (M1/M2/M3):** pick the `arm64` package
   - **Intel Mac:** pick the `x86_64` package
3. Open the downloaded `.pkg` and click through the installer

To verify R installed correctly, open **Terminal** and run:
```
R --version
```
You should see something like `R version 4.x.x`.

---

### Step 2 — Install Jupyter

In Terminal:
```
pip3 install jupyterlab
```

If you get a `command not found: pip3` error, first install Python from **https://www.python.org/downloads/**, then retry.

---

### Step 3 — Register the R kernel

This is the step that lets Jupyter and VS Code know R exists. You only do this once.

Open Terminal and start an R session:
```
R
```

You will see an `>` prompt. Paste these two lines:
```r
install.packages("IRkernel")
IRkernel::installspec()
```

When asked to choose a CRAN mirror, type `1` and press Enter. Wait for it to finish, then type `q()` to quit R.

---

### Step 4 — Get the notebook

**Option A — Clone with git:**
```
git clone https://github.com/agurjar123/cbab-bootcamp.git
cd cbab-bootcamp
```

**Option B — Download manually:**
1. Go to **https://github.com/agurjar123/cbab-bootcamp**
2. Click the green **Code** button → **Download ZIP**
3. Unzip the folder

---

### Step 5 — Open the notebook

**In JupyterLab:**
```
jupyter lab
```
A browser window opens. Navigate to `homework/` and click `HW1_scRNAseq_student.ipynb`.

**In VS Code:**
1. Install VS Code from **https://code.visualstudio.com**
2. Open VS Code → Extensions (left sidebar) → search `Jupyter` → Install
3. Open the `cbab-bootcamp` folder in VS Code (File → Open Folder)
4. Navigate to `homework/HW1_scRNAseq_student.ipynb` and click it
5. In the top-right corner click **Select Kernel** → **Jupyter Kernel** → **R**

---

## Windows

### Step 1 — Install R

1. Go to **https://cran.r-project.org/bin/windows/base/**
2. Click **Download R x.x.x for Windows** and run the installer
3. Leave all default options as-is and click through

To verify, open **Command Prompt** (`Win + R` → type `cmd` → Enter) and run:
```
R --version
```

---

### Step 2 — Install Python and Jupyter

1. Go to **https://www.python.org/downloads/**
2. Download and run the installer
3. On the first screen, check **"Add Python to PATH"** (important!)
4. Click **Install Now**

Then in Command Prompt:
```
pip install jupyterlab
```

---

### Step 3 — Register the R kernel

Open Command Prompt and start R:
```
R
```

At the `>` prompt:
```r
install.packages("IRkernel")
IRkernel::installspec()
```

Type `q()` when done.

---

### Step 4 — Get the notebook

**Option A — Clone with git** (if you have git installed):
```
git clone https://github.com/agurjar123/cbab-bootcamp.git
cd cbab-bootcamp
```

**Option B — Download manually:**
1. Go to **https://github.com/agurjar123/cbab-bootcamp**
2. Click the green **Code** button → **Download ZIP**
3. Unzip the folder

---

### Step 5 — Open the notebook

**In JupyterLab:**
```
jupyter lab
```

**In VS Code:**
1. Install VS Code from **https://code.visualstudio.com**
2. Extensions → search `Jupyter` → Install
3. File → Open Folder → select `cbab-bootcamp`
4. Open `homework/HW1_scRNAseq_student.ipynb`
5. Top-right → **Select Kernel** → **Jupyter Kernel** → **R**

---

## Verify everything works

Once the notebook is open and the R kernel is selected, run the first cell (the setup cell). It will install Seurat, dplyr, and patchwork. At the end you should see:

```
Seurat version: 5.x.x
```

If you see that, you're ready to go. Run cells from top to bottom.

---

## Common problems

**`jupyter: command not found` after installing:**
Close and reopen your terminal, then try again. If still broken, try `python3 -m jupyterlab` instead.

**`R: command not found` in terminal (Mac):**
R installed but isn't on your PATH. Try opening the **R application** directly from your Applications folder to run the IRkernel steps.

**Kernel shows as "R" but immediately dies when running a cell:**
Re-run `IRkernel::installspec()` in R, then restart VS Code or JupyterLab completely.

**Package installation fails with compilation errors (Windows):**
Install **Rtools** from **https://cran.r-project.org/bin/windows/Rtools/**, then retry.

**"This version of R is not set up to install source packages" (Linux):**
Your R was installed via a system package manager (e.g. `dnf`, `yum`) and is missing the development headers needed to compile packages. The notebook's setup cell handles this automatically by using pre-built binaries — but you need the latest version of the notebook. Re-download it from GitHub and try again. If the error persists, install the R development headers manually:
```
# Fedora / RHEL / Rocky / AlmaLinux
sudo dnf install R-devel

# Ubuntu / Debian
sudo apt install r-base-dev
```
