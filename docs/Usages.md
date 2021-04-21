---
title: Usages
nav_order: 7
---

## Robocup ROS Workspace Basics
1. Head to robocup_ws (workspace):   
`cd robocup_ws`  
2. Build dependencies and packages:  
`catkin_make`  
3. Source the project so that ROS can locate all packages:  
`source devel/setup.bash`  
4. Once in **/src**, run:  
`roslaunch robocup_gazebo robocup_world.launch`  
<div align="center"> 
<br />  
</div>

## Run the game master and game simulator
1. source the base ROS
2. catkin_make the workspace
3. source workspace build
4. using ros launch:
    - go to workspace dir
    -  ```roslaunch GameEngine game.launch```
5. Or using ros run:
    - go to workspace dir
    - ```rosmaster```
    - ```rosrun GameEngine game_master.py```
    - ```rosrun GameEngine game_simulator.py```
    
<br />

## Configure the PyCharm development environment

### Add alias 
1.For ROS
2. For PyCharm

### PyCharm - setting the project
1. In Pycharm open project with UofG_Robotics_TDP as a source folder
2. ``file -> Settings -> Project: UofG_Robotics_TDP -> Project Structure``
3. Right click on ```robotcap_ws``` folder and click on ```source```

### Pre-requirements 
1. Install PyCharm
2. Create an alias to Pycharm 
3. Create an alias to main ROS source

### Setup
1. Source base ROS
2. from same terminal launch PyCharm
3. Create a virtual environemtn (call it: ```.venv```)
4. Create launch configuration
    - change the launch directory to GameEngine
    
...to be continue

1) git clone
2) git checkout speccific branch
3) source base ROS ```source /opt/ros/__vrsion__/setup.bash```
4) cd robotcup
5) catkin_make
6) source devel/setup.bash
7) cd ../
8) sudo pip3 install -r requirements.txt (if pip3 is not working install it)
9) cd robotcup
10) roslaunch GameEngine game.launch


### How to test:
Simple ros launch:

```roslaunch GameEngine game.launch```

ros launch with the ball init position at x = 1, y = 2 in world coordinate system 

```roslaunch GameEngine game.launch simulator_args:="--ball_pos 1 2"```

ros launch with the ball init position at x = 1, y = 2 (in world coordinate system) and vel x = 0 y = 0.4

```roslaunch GameEngine game.launch simulator_args:="--ball_pos 0.5 0.5 --ball_vel 0 0.4"```

ros launch with team 1 at new positions: player1_x, player1_y, player2_x, player2_y, ... , player5_y

```roslaunch GameEngine game.launch simulator_args:="--team_1_init_pos -2 2 -2 -2 2 1 2 -1 -4 0"```
