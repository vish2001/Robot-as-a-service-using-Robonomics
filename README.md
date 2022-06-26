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

Open robonomics parachain portal: https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Fkusama.rpc.robonomics.network%2F#/explorer

and switch to local node.![Screenshot from 2022-06-26 22-32-37](https://user-images.githubusercontent.com/55589910/175825558-d264def3-ce1e-4a4e-b6a1-218811b350ce.png)

Then go to Accounts and create KUKA account. Save account's mnemonic key, you will need it later.

![Screenshot from 2022-06-26 22-36-52](https://user-images.githubusercontent.com/55589910/175825647-b628e7d8-7df3-4273-b48c-6f5b97dce344.png)

Send some units to the new account from one of default accounts.

![Screenshot from 2022-06-26 22-38-43](https://user-images.githubusercontent.com/55589910/175825830-11dfe8cc-e3f8-4e24-9144-49749ee9e7e8.png)

In config directory in kuka_control package you need to create config file with this lines, where <your_mnemonic> is saved mnemonic seed:

{
    "kuka_mnemonic": "<your_mnemonic>",
    "node": "ws://127.0.0.1:9944"
}


