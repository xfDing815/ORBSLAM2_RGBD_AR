![](https://github.com/xfDing815/ORBSLAM2_RGBD_AR/blob/main/images/RGBD_AR.png)

# This project is used for RGBD camera to generate virtual AR. In ROS environment, Realsensed435i camera can be equipped to run Mono, Stereo, RGBD, and Mono_AR, RGBD_ AR, and can be tested on the TUM dataset.

# 1. Prerequisites
At first, you should build the workspace
You should have:
```
eigen for version 3
Pangolin for version 0.6
opencv for version 3.2.0
ros for melodic
```

Then establishing a workspace
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src
catkin_init_workspace
cd ~/catkin_ws/
catkin_make
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
git clone https://github.com/xfDing815/ORBSLAM2_RGBD_AR.git ORB_SLAM2
```
# 2. Clone the repository:
```
git clone https://github.com/xfDing815/ORBSLAM2_RGBD_AR.git ORB_SLAM2
```

# 3.From https://github.com/raulmur/ORB_SLAM2 to download Vocabulary
move the Vocabulary into ORB_SLAM2

# 4. Build
```
chmod +x build.sh build_ros.sh
./build.sh
./build_ros.sh
```

# 5. Run this demo with the [rgbd-dataset](https://cvg.cit.tum.de/data/datasets/rgbd-dataset/download#freiburg1_room) 
```
roscore
rosrun ORB_SLAM2 RGBDAR Vocabulary/ORBvoc.txt Examples/RGB-D/TUM1_ROS.yaml
rosbag play rgbd_dataset_freiburg1_room.bag /camera/rgb/image_color:=/camera/rgb/image_raw /camera/depth/image:=/camera/depth_registered/image_raw

```

