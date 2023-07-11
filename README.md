![](https://github.com/xfDing815/ORBSLAM2_RGBD_AR/blob/main/images/RGBD_AR.png)

# 1. Prerequisites
You

Establishing a workspace
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

# 3. from https://github.com/raulmur/ORB_SLAM2 to download Vocabulary
move the Vocabulary into ORB_SLAM2

# 4. build
```
chmod +x build.sh build_ros.sh
./build.sh
./build_ros.sh
```

# 5. run this demo with the [rgbd-dataset](https://cvg.cit.tum.de/data/datasets/rgbd-dataset/download#freiburg1_room) 
```
roscore
rosrun ORB_SLAM2 RGBDAR Vocabulary/ORBvoc.txt Examples/RGB-D/TUM1_ROS.yaml
rosbag play rgbd_dataset_freiburg1_room.bag /camera/rgb/image_color:=/camera/rgb/image_raw /camera/depth/image:=/camera/depth_registered/image_raw

```

