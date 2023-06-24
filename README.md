# Contact Forces in MuJoCo - Franka Panda

**!!! WARNING !!!** This branch doesn't work correctly (contact forces are noisy / oscillate heavily), so **do not use it.** 
It was created to showcase the problem raised in [MuJoCo issue 941](https://github.com/deepmind/mujoco/issues/941).
The main branch provides a solution and is working fine.

Alternatively, a different set of collision geoms can be used and force measurements will be noise-free too.
To do so, comment in [this](https://github.com/llach/franka_force/blob/oscillations/franka_force.xml#L85) and [this](https://github.com/llach/franka_force/blob/oscillations/franka_force.xml#L98) and comment out the other geoms [here](https://github.com/llach/franka_force/blob/oscillations/franka_force.xml#L82) and [here](https://github.com/llach/franka_force/blob/oscillations/franka_force.xml#L95).

---

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
