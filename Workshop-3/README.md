# 🏁 Autonomous Racing Workshop 3: Deep Q-Network (DQN) Implementation

This repository contains a complete implementation of Deep Q-Network (DQN) for the CarRacing-v3 environment using Stable-Baselines3. The project demonstrates reinforcement learning techniques applied to autonomous car racing simulation.

## 📋 Project Overview

This workshop focuses on training an AI agent to autonomously navigate and race in the Gymnasium CarRacing environment using Deep Q-Network (DQN) algorithm. The implementation includes:

- **DQN Training Pipeline**: Complete training setup with evaluation callbacks
- **Environment Preprocessing**: Frame stacking and image processing for optimal learning
- **Performance Monitoring**: Training progress visualization and model evaluation
- **Video Recording**: Capability to record and analyze trained agent performance

## 📁 Repository Structure

```
Workshop-3/
├── car_racing/
│   └── [Car_Racing]_Deep_Q_Network_(DQN).ipynb    # Main DQN implementation notebook
├── logs/                                          # Training logs and saved models (generated)
├── videos/                                        # Recorded gameplay videos (generated)
├── environment-linux.yml                         # Conda environment for Linux systems
├── environment-windows.yml                       # Conda environment for Windows systems
└── README.md                                      # This documentation
```

### 📓 Key Files

- **[Main Notebook](car_racing/[Car_Racing]_Deep_Q_Network_(DQN).ipynb)**: Complete DQN implementation with training, evaluation, and visualization
- **[Linux Environment](car_racing/environment.yml)**: Conda environment configuration tested on Linux systems
- **[Windows Environment](car_racing/environmentWIN.yml)**: Conda environment configuration for Windows systems
- **[Example Video](videos/best_model_car_racing_dqn.mp4)**: Example video of the trained agent (generated after running the notebook)

## 🖥️ Environment Setup

### Prerequisites

Make sure you have **Miniconda** or **Anaconda** installed:  
👉 [Download Miniconda](https://docs.conda.io/en/latest/miniconda.html)

### 🐧 Linux Setup (Tested)

The project has been successfully trained and tested on Linux systems:

```bash
# Create environment from Linux configuration
conda env create -f environment.yml
conda activate car-racing

# Launch Jupyter Notebook
jupyter notebook
```

### 🪟 Windows Setup

Windows environment configuration is provided but not yet fully tested:

```bash
# Create environment from Windows configuration
conda env create -f environmentWIN.yml
conda activate car-racing

# Launch Jupyter Notebook
jupyter notebook
```


## 🚀 Getting Started

1. **Clone the repository**:

   ```bash
   git clone <repository-url>
   cd AutonomousRacing/Workshop-3
   ```

2. **Set up the environment** (choose your OS):

   ```bash
   # For Linux (recommended)
   conda env create -f environment.yml
   conda activate car-racing
   
   # For Windows (experimental)
   conda env create -f environmentWIN.yml
   conda activate car-racing
   ```

3. **Launch Jupyter Notebook**:

   ```bash
   jupyter notebook
   ```

4. **Open and run the main notebook**:
   Navigate to `car_racing/[Car_Racing]_Deep_Q_Network_(DQN).ipynb` and execute the cells sequentially.

## 🧠 DQN Implementation Details

### Key Features

- **Environment**: CarRacing-v3 (discrete actions)
- **Algorithm**: Deep Q-Network (DQN) with experience replay
- **Preprocessing**: 84x84 grayscale conversion with frame stacking (4 frames)
- **Network**: CNN policy for handling visual input
- **Training**: 750,000 timesteps with evaluation every 25,000 steps

### Training Configuration

- **Buffer Size**: 150,000 (encourages exploration)
- **Frame Stack**: 4 consecutive frames for temporal information
- **Evaluation**: 20 episodes every 25,000 training steps
- **Best Model**: Automatically saved based on evaluation performance

## 📊 Results and Monitoring

The implementation includes comprehensive monitoring:

- **Training Progress**: Real-time progress bars during training
- **Performance Plots**: Mean reward evolution over training timesteps
- **Video Recording**: Automated recording of best model gameplay
- **Model Evaluation**: Statistical analysis with mean ± standard deviation

## 🛠️ Troubleshooting

### Common Issues

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

#### Missing Dependencies
Install additional packages if needed:

```bash
pip install opencv-python
pip install 'stable-baselines3[extra]'
```

If you run into missing package errors, here are some common fixes:

### 📸 OpenCV Missing

```bash
pip install opencv-python
# or for headless environments:
pip install opencv-python-headless
```
## ✅ Optional: Additional Recommended Packages

```bash
pip install gymnasium[box2d] pygame
pip install imageio scikit-image
pip install seaborn
```
---
## ✅ Optional: Additional Recommended Packages

```bash
pip install gymnasium[box2d] pygame
pip install imageio scikit-image
pip install seaborn
```

---

## 🔧 Customization

You can modify the training parameters in the notebook:

- **Training Duration**: Adjust `total_timesteps` in the `model.learn()` call
- **Buffer Size**: Modify `buffer_size` in DQN initialization
- **Evaluation Frequency**: Change `eval_freq` in EvalCallback
- **Environment Settings**: Modify `env_kwargs_dict` for different configurations





## 📚 References

- [Stable-Baselines3 Documentation](https://stable-baselines3.readthedocs.io/)
- [Gymnasium CarRacing Environment](https://gymnasium.farama.org/environments/box2d/car_racing/)
- [Deep Q-Network Paper](https://arxiv.org/abs/1312.5602)

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