# Contact Forces in MuJoCo - Franka Panda

Example of how to read contact forces during a grasp with the [Franka Panda hand model](https://github.com/deepmind/mujoco_menagerie/blob/main/franka_emika_panda/hand.xml) from the [MuJoCo Menagerie](https://github.com/deepmind/mujoco_menagerie). 
The original MJCF was adapted slightly:

- control range changed from [0, 255] to [0, 0.045]
- fingers close independently (removed tendons and equality constraint)
- add names for the finger's collision pads
- add visuals, e.g. the ground plane, and lighting
- add grasping object

## Instructions

Run `franka.py`. 
If `with_vis=False`, the grasp is executed and the resulting force trajectory is plotted.
Set it to `True` to see the grasp.

## Oscillating Forces

On the [`oscillations` branch ](https://github.com/llach/franka_force/tree/oscillations) of this repo lies a version of the gripper producing unstable contact force readings during the grasp. 