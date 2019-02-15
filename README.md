# simple_arm_robot

This project developed for learning how to write nodes in C++

The first node, simple_mover. The simple_mover node does nothing more than publish joint angle commands to simple_arm.

The second node, arm_mover. The arm_mover node provides a service called safe_move, which allows the arm to be moved to any position within its workspace that has been deemed safe. The safe zone is bounded by minimum and maximum joint angles, and is configurable via the ROS parameter server.

The last node, look_away node. This node subscribes to the arm joint positions and a topic where camera data is being published. When the camera detects an image with uniform color, meaning that it’s looking at the sky, and the arm is not moving, the node will call the safe_move service via a client to move the arm to a new position.
