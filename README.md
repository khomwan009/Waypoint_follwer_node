source install/setup.bash
ros2 launch xsens_mti_ros2_driver xsens_ublox.launch.py

/usr/bin/python /home/mag/Peach/src/way_point/nav_path.py

source /opt/ros/humble/setup.bash
python3 src/way_point/Adaptive Waypoint Follower And Pure Pursuit Node.py

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
"# Waypoint-Follwer-Node" 
"# Waypoint-Follwer-Node" 
"# Waypoint-Follwer-Node" 
