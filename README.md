# setup_localization

bag//

mapping
cd ros_codes/catkin_ws/; source devel/setup.bash
roslaunch gmapping rp_gmapping_runtime.launch && python recode_uwb.py

mapfile odom_init.txt uwb_init.txt
cp  uwb_init.txt modules/perception/localization/config/

pointcloud

roslaunch mrpt_icp_2d_slam icp_slam_rplidar.launch
cd ros_codes/qt_ws; source devel/setup.bash
rosrun laser_detection pointcloud_save
cp map_pointcloud src/laser_detection/map_cloud
