# Robotics-and-AI-Department-tasks4.1
Robotics-and-AI-Department-tasks4.1
<br/>
<br/>
In this task we will use SLAM map to launch the navigation.
<br/>
In the previous SLAM task, TurtleBot3 World is used to creat a map.
<br/>
The same Gazebo environment will be used for Navigation.
<br/>
![image](https://user-images.githubusercontent.com/23351217/127600063-e5388b63-fd54-4b9e-acc4-17ea1d2184a1.png)
<br/>
we will need this files
<br/>
first we need to Launch Simulation World by use this command
```ruby
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
![image](https://user-images.githubusercontent.com/23351217/127600396-0bdb03f5-fa01-4397-bb36-34a640980626.png)
<br/>
then we will Run Navigation Node
lets open new terminal and use this command
```ruby
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```
![image](https://user-images.githubusercontent.com/23351217/127600625-56ea900a-4883-4a0c-b98b-be41a7f415a2.png)
<br/>
Initial Pose Estimation must be performed before running the Navigation as this process initializes the AMCL parameters that are critical in Navigation.
<br/>
TurtleBot3 has to be correctly located on the map with the LDS sensor data that neatly overlaps the displayed map.
<br/> 
we will do this steps.
<br/> 
1-Click the <b>2D Pose Estimate</b> button in the RViz menu.<br/> 

2-Click on the map where the actual robot is located and drag the large green arrow toward the direction where the robot is facing.<br/> 

3-Repeat step 1 and 2 until the LDS sensor data is overlayed on the saved map.<br/> 

4-Launch keyboard teleoperation node to precisely locate the robot on the map.<br/> 
```ruby
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
5-Move the robot back and forth a bit to collect the surrounding environment information and narrow down the estimated location of the TurtleBot3 on the map which is displayed with tiny green arrows.
<br/>
6-Terminate the keyboard teleoperation node by entering Ctrl + C to the teleop node terminal in order to prevent different cmd_vel values are published from multiple nodes during Navigation.
<br/>
![image](https://user-images.githubusercontent.com/23351217/127601614-9e69eb42-0c03-4565-b6a8-4e903f786be7.png)
<br/>
to Set Navigation Goal
<br/>
1-Click the 2D Nav Goal button in the RViz menu.
<br/>
2-Click on the map to set the destination of the robot and drag the green arrow toward the direction where the robot will be facing.<br/>

This green arrow is a marker that can specify the destination of the robot.<br/>

The root of the arrow is x, y coordinate of the destination, and the angle θ is determined by the orientation of the arrow.<br/>

As soon as x, y, θ are set, TurtleBot3 will start moving to the destination immediately.<br/>

![image](https://user-images.githubusercontent.com/23351217/127601884-a020cd36-ec6a-4557-a811-ab0e209229cd.png)
