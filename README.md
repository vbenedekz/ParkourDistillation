# Universal Parkour Policy on Unitree Go2

## Objective
The goal of this project, is to create a system that learns a single, end-to-end parkour policy based on vision. It should perform a variety of parkour moves using a simple reward system, without needing any reference motion data.
We will create a reinforcement learning method, to teach skills like climbing over tall obstacles, jumping across wide gaps, crawling under low barriers, squeezing through narrow spaces, and running.
These skills are combined into one vision-based parkour policy, which we willtransfer to our quadrupedal robot, the Unitree Go2 using its front-facing depth camera.

## Installation
- Install Isaac Lab by following the [installation guide](https://isaac-sim.github.io/IsaacLab/main/source/setup/installation/index.html).
  We recommend using the conda installation as it simplifies calling Python scripts from the terminal.

- Clone or copy this project/repository separately from the Isaac Lab installation (i.e. outside the `IsaacLab` directory):

- Using a python interpreter that has Isaac Lab installed, install the library in editable mode using:

    ```bash
    # use 'PATH_TO_isaaclab.sh|bat -p' instead of 'python' if Isaac Lab is not installed in Python venv or conda
    python -m pip install -e source/parkour_distillation
    ```

- Verify that the extension is correctly installed by:

    - Listing the available tasks:

        Note: It the task name changes, it may be necessary to update the search pattern `"Template-"`
        (in the `scripts/list_envs.py` file) so that it can be listed.

        ```bash
        # use 'FULL_PATH_TO_isaaclab.sh|bat -p' instead of 'python' if Isaac Lab is not installed in Python venv or conda
        python scripts/list_envs.py
        ```

    - Running a task:

        ```bash
        # use 'FULL_PATH_TO_isaaclab.sh|bat -p' instead of 'python' if Isaac Lab is not installed in Python venv or conda
        python scripts/<RL_LIBRARY>/train.py --task=<TASK_NAME>
        ```

    - Running a task with dummy agents:

        These include dummy agents that output zero or random agents. They are useful to ensure that the environments are configured correctly.

        - Zero-action agent

            ```bash
            # use 'FULL_PATH_TO_isaaclab.sh|bat -p' instead of 'python' if Isaac Lab is not installed in Python venv or conda
            python scripts/zero_agent.py --task=<TASK_NAME>
            ```
        - Random-action agent

            ```bash
            # use 'FULL_PATH_TO_isaaclab.sh|bat -p' instead of 'python' if Isaac Lab is not installed in Python venv or conda
            python scripts/random_agent.py --task=<TASK_NAME>
            ```

## Resources

- [Robot Parkour Learning](https://robot-parkour.github.io/)
- [Extreme Parkour with Legged Robots](https://extreme-parkour.github.io/)
- [Learning To Walk in Minutes](https://leggedrobotics.github.io/legged_gym/)
- [Isaac Lab Documentation](https://isaac-sim.github.io/IsaacLab/main/index.html#)