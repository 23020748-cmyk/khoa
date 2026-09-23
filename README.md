#huongdan
cd ~/ros2_ws
source /opt/ros/humble/setup.bash

colcon build --packages-select ur_letter_drawer --symlink-install --parallel-workers 1
source install/setup.bash

export LIBGL_ALWAYS_SOFTWARE=1
export IGN_GAZEBO_RESOURCE_PATH=/usr/share/ignition/ignition-gazebo6/worlds${IGN_GAZEBO_RESOURCE_PATH:+:$IGN_GAZEBO_RESOURCE_PATH}

ros2 launch ur_letter_drawer draw_k_sim.launch.py
