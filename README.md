# Task Transfor for Robotics

### Planning with Diffusion for Flexible Behavior Synthesis – Diffuser:
GitHub: https://github.com/jannerm/diffuser/tree/maze2d 
1. Install MuJoco with this guide: https://gist.github.com/saratrajput/60b1310fe9d9df664f9983b38b50d5da
    * If a libGL error exists:
        * Check out this solution: https://askubuntu.com/questions/1184581/error-libgl-error-no-matching-fbconfigs-or-visuals-found-libgl-error-fail
        * Ensure libglew-dev Is installed
        * Add to bashrc: ```export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so``` and ```source .bashrc```
        * Open a window: ```xvfb-run -a -s "-screen 0 1400x900x24" bash```
2. Clone the above repo
3. Setup conda environment with the following changes contained in ```diffuser_environment.yml```
4. Can modify configurations in config.maze2d
5. Run training command from GitHub modifying parameters as needed
    * May have to include the file imports into the system path. Add the following ```sys.path.append(os.getcwd())``` to beginning of script
    * In ```~/diffuser/datasets/buffer.py``` change ```np.int``` to ```int``` everywhere as it is not deprecated
    * If you encounter a cython compilation error, downgrade your cyton via ```pip install "cython<3"``` (https://github.com/openai/mujoco-py/issues/773)
6. Once a dataset is trained, you can then perform planning


### Offline Reinforcement Learning with Implicit Q-Learning - IQL:
GitHub:
- Official TensorFlow, Jax implementation -  https://github.com/ikostrikov/implicit_q_learning
- PyTorch version I used -  https://github.com/gwthomas/IQL-PyTorch/tree/main

1.	Ensure MuJoco Gym is installed
2.	Clone repo above
3.	Setup conda environment with attached environment file: ```iql_environment.yml```
5.	Should be all set to run training script from GitHub
6.	To get results, first train and then run ```results.py``` with the directory where training had been saved and environments to evaluate
