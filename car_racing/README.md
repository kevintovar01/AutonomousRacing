# 🏁 Car Racing Environment Setup with Conda

This guide explains how to set up a development environment for reinforcement learning experiments using the `CarRacing-v3` environment (from Gymnasium) and Stable-Baselines3, using **Miniconda** for dependency management.

## ✅ Prerequisites

Make sure you have **Miniconda** installed. You can download it from:  
👉 https://docs.conda.io/en/latest/miniconda.html


## 📦 Step 1: Create and Activate the Conda Environment

Create a new Conda environment with Python 3.10 (to avoid deprecated package issues):

```bash
conda create -n car_racing python=3.10
conda activate car_racing
```

---

## 📚 Step 2: Install Basic Dependencies

Install common scientific packages (you can skip this if you're installing from `environment.yml`):

```bash
conda install jupyter pandas numpy matplotlib
```

---

## 📄 Step 3: (Optional) Install from `environment.yml`

If you already have a predefined environment file:

```bash
conda env create -f environment.yml
conda activate car_racing
```

---

## 🚀 Step 4: Launch Jupyter Notebook

If you're ready to start working in notebooks:

```bash
jupyter notebook
```

### ⚠️ Box2D / GLIBCXX Compatibility Error

If you encounter an error like:

```
ImportError: /path/to/libstdc++.so.6: version `GLIBCXX_3.4.32` not found
```

It’s likely due to an outdated version of `libstdc++.so.6`. You can work around it by explicitly setting the preload path to a newer version:

```bash
LD_PRELOAD=/usr/lib/libstdc++.so.6 jupyter notebook
```

Make sure the path to `libstdc++.so.6` matches the updated version available on your system (you can locate it using `locate libstdc++.so.6` or `find /usr -name libstdc++.so.6`).

---

## 🧩 Step 5: Install Missing Python Packages

If you run into missing package errors, here are some common fixes:

### 📸 OpenCV Missing

```bash
pip install opencv-python
# or for headless environments:
pip install opencv-python-headless
```

### 📊 TQDM / Rich Missing (for progress bar support)

```bash
pip install 'stable-baselines3[extra]'
```

This installs extra tools such as `tqdm`, `rich`, `tensorboard`, and others used by Stable-Baselines3 for monitoring and visualization.

---

## ✅ Optional: Additional Recommended Packages

```bash
pip install gymnasium[box2d] pygame
pip install imageio scikit-image
pip install seaborn
```

---

## 🧠 Summary

- ✅ Use Python 3.10 to avoid compatibility issues
- 📚 Use `LD_PRELOAD` if `GLIBCXX` errors occur
- 🚀 Install extra packages for visualization and rendering
- 📊 Use `stable-baselines3[extra]` to get full functionality

---

## 🛠️ Troubleshooting

If you encounter other dependency errors, try updating your system packages and ensuring that your Conda environment is isolated from global Python installations. You can also export your current environment with:

```bash
conda env export > environment.yml
```

This will allow you (or others) to recreate the exact same environment in the future.

---

## 🤖 Author

This environment was configured for reinforcement learning with the `CarRacing-v3` Gymnasium environment.

Feel free to contribute or suggest improvements!
