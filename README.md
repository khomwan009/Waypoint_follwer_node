source install/setup.bash
ros2 launch xsens_mti_ros2_driver xsens_ublox.launch.py

/usr/bin/python /home/mag/Peach/src/way_point/nav_path.py

python3 src/way_point/way_point.py --ros-args -p use_desired_path_gate:=true

source /opt/ros/humble/setup.bash
python3 src/way_point/PP_CTE.py


---------------------------------------------
cd Ouster
source install/setup.bash 
ros2 launch ouster_ros driver.launch.py 


cd 1Localize
source install/setup.bash 
ros2 launch lidar_localization_ros2 lidar_localization.launch.py 

-------------------------------------------------
ros2 run rqt_tf_tree rqt_tf_tree

source install/setup.bash 
ros2 launch teleop_twist_joy teleop-launch.py joy_config:='xbox'

ros2 bag record -a

ros2 bag play my_bag

/usr/bin/python /home/mag/Peach/src/cmd_vel_joy.py

sudo ip link set can0 down
sudo ip link set can0 up type can bitrate 250000 restart-ms 100
sudo cansend can0 123#DEADBEEF
sudo ip -details -statistics link show can0

sudo ip link set can2 down
sudo ip link set can2 up type can bitrate 250000 restart-ms 100
sudo cansend can2 123#DEADBEEF
sudo ip -details -statistics link show can2

source install/setup.bash 
/bin/python /home/mag/Peach/src/can_gsusb.py

sudo ip addr flush dev eno1
sudo ip addr add 192.168.50.20/24 dev eno1
sudo ip link set eno1 up
# Waypoint_follwer_node
"# Waypoint_follwer_node" 
