# Robot-as-a-service-using-Robonomics

## REQUIREMENTS:

=>ROS melodic, Gazebo 

=>Some extra packages:
 `sudo apt-get install ros-melodic-gazebo-ros-control ros-melodic-effort-controllers ros-melodic-joint-state-controller`

=>IPFS 0.4.22

`tar -xvzf go-ipfs_v0.4.22_linux-386.tar.gz`

`cd go-ipfs/`

`sudo bash install.sh`

`ipfs init`

=>ipfshttpclient

`pip3 install ipfshttpclient`

=>substrate-interface

`pip3 install substrate-interface`

=>Robonomics node (binary file):https://github.com/airalab/robonomics/releases

## Running the model:

`roslaunch manipulator_gazebo manipulator_empty_world.launch`

`rosrun manipulator_gazebo move_arm_server`

`./robonomics --dev --tmp`

`ipfs daemon`

`rosrun kuka_controller move_arm_client.py`
