## 1.Visualize UR3 Robot using urdf_tutorial
### →Firstly create a workspace
- cd mkdir -p ur3robot_ws/src 
- cd ur3robot_ws/ 
- colcon build 
- source install/setup.bash

### →Create a package into the src folder of ur3robot_ws
- ros2 pkg create --build-type ament_cmake ur3robot_description
- cd ~/ur3robot_ws
- colcon build
- source install/setup.bash

### →Create a folder as a name of meshes into ur3robot_description
- copy .STL files into this folder
- https://github.com/Sadek-13/Voice-Controlled-UR3-Robot/tree/1439072f517162ff9d9a78689a833f3006a45b78/src/ur3robot_description/meshes

### →Create another folder as a name of urdf into ur3robot_description
- create a xacro file as a name of ur3robot.urdf.xacro
- write this code into this file:
![Image](https://github.com/user-attachments/assets/5dc85cb4-9d97-4d28-b551-7b16c4d5a061)

### →Update the code of CMakeLists.txt 
![Image](https://github.com/user-attachments/assets/d7103764-cfab-4f49-a653-865fb6598a61)

### →Install urdf tutorial pkg into urdf_description folder
- sudo apt-get install ros-humble-urdf-tutorial
  
### →Visualize the code into rviz2(help of urdf_tutorial)
- ros2 launch urdf_tutorial display.launch.py model:=/home/golam_sadek/ur3robot_ws/src/ur3robot_description/urdf/ur3robot.urdf.xacro
![Image](https://github.com/user-attachments/assets/e8f7961e-b7c4-43b1-9e52-edd6684720e7)

## 2.Visualize UR3 Robot without using urdf_tutorial
### →Create a folder as a name of launch into ur3robot_description
- create a python launch file (display.launch.py)
- write below's code:
- https://github.com/Sadek-13/Voice-Controlled-UR3-Robot/blob/ef393d4e30d577bc7524c7109e6ac99b7993c8be/src/ur3robot_description/launch/display.launch.py
  
### →update CMakeList.txt file
![Image](https://github.com/user-attachments/assets/0eeaf19e-9541-478c-9ff6-f8fed87ad06c)

### →update package.xml file
![Image](https://github.com/user-attachments/assets/148a51c9-5f62-4078-a11e-7cf5886e69e9)

### →Run below's command
ros2 launch ur3robot_description display.launch.py

![Image](https://github.com/user-attachments/assets/e8f7961e-b7c4-43b1-9e52-edd6684720e7)

## 3.Spawn the UR3 robot into Gazebo
### →Add the collision and inertial tag into the ur3robot.urdf.xacro file
[image.docx.pdf](https://github.com/user-attachments/files/19685258/image.docx.pdf)

### →create a new file into launch folder (gazebo.launch.py)
https://github.com/Sadek-13/Voice-Controlled-UR3-Robot/blob/f3b6bfee66e17922bbcc27fb39530071b9d9fe58/src/ur3robot_description/launch/gazebo.launch.py

### →Update package.xml file
![Image](https://github.com/user-attachments/assets/a42b358c-e7f6-4cc7-9d16-8ff808923b91)

### →Run below's command on Terminal
ros2 launch ur3robot_description gazebo.launch.py 

![Image](https://github.com/user-attachments/assets/c645bcf9-f25d-4f9a-97f9-4b0e1c63ad2c)

## 4.Control the spawned robot using ros_control
## →Create a new xacro file( ur3robot_gazebo.xacro)

## →Connect this xacro file with ur3robot.urdf.xacro
![Image](https://github.com/user-attachments/assets/987e5854-9b3d-4348-9784-ed6b5134eb60)





