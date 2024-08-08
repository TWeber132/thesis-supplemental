# Supplemental material for my masters thesis

In the folders nerf and grasp are both architecual and validation information.

---
The simulated tasks are heavily based on the work of Ravens which is a collection of simulated tasks in PyBullet and CLIPort.
### Simulated task
In the context of this thesis, a simulated task consists of an environment, a robot, a robotic gripper, and the task itself.  Robot and gripper are designed to be interchangeable. Only the joint and the pose of the joint the robot attaches to the environment has to be know. Aswell as the joint and the pose of this joint the gripper attaches to the robot at. For the environment, the robot, and the gripper, a URDF file must be provided. The environment, the robot and the robotic gripper all are defined as class objects, that load the corresponding urdf during object initialization. Every class contains methods that handle object specific behavior. The robot can move to either a TCP point or to axis angles, the gripper can open or close, and the environment can, for example, spawn or delete manipulation objects. Manipulation objects are items within the scene or task boundaries that the robot is intended to grip. The type of manipulation object and the way the robot interacts with them are task-dependent and can vary greatly. Moreover, the interaction between the robot and the manipulation object is also dependent on the type of gripper used. So-called primitives organize this discrepancy.


### Tasks -  pick-seen-google-object
From 1 to 5 objects can be spawned at a time, only one object will be picked by the robot. The oracle that tries to provide a correct grasp pose is implemented inside every Task. The reasoning behind this is that every Task provides a unique problem which also requires a unique solution. At this point in time, only one task exists but because of the base class it is based on, it should be simple enough to implement additional tasks. Inspiration can be taken from CLIPort GitHub.