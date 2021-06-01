
# Azure Hardware & SDK Setup
Use [this link](https://docs.microsoft.com/en-us/azure/kinect-dk/set-up-azure-kinect-dk)
Essentially, you need to install 3 packages
```
sudo apt-get install libk4a1.4
sudo apt-get install libk4a1.4-dev 
sudo apt-get install k4a-tools
Note: replace the 1.4 with whatever version you got in the release.
```
Note: in order to run Azure without sudo, the following steps are necessary at the end:

- [x] Copy ['scripts/99-k4a.rules'](https://github.com/microsoft/Azure-Kinect-Sensor-SDK/blob/develop/scripts/99-k4a.rules) into '/etc/udev/rules.d/'.
- [x] Detach and reattach Azure Kinect devices if attached during this process.

# Azure ROS Setup
Follow [this link](https://vinesmsuic.github.io/2020/12/25/azure-kinect-ros-setup/#azure-kinect-ros-driver)

# Record a Bag file
```
cd record_kinnect_bags/launch
roslaunch spawn_kinnect.launch
```
On another terminal: 
```
roslaunch record_spawn_kinnect.launch
```

# rtab_map SLAM on a reccorded bag file
Play the bag file, then 

```
roslaunch launch_slam_rtabmap.launch
```
