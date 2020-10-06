# TURTLEBOT3 EXPERIMENTS

The following instructions are built for Melodic devel but it should work for all devels supported by Turtlebot3.

## INSTALLATION

1. Clone this repository into the `workspace/src`
2.  Goto workspace directory: `cd ../`
3. Run `catkin_make`

## DEPENDENCIES

1. `sudo apt-get install ros-melodic-turtlebot3-msgs`
2. `sudo apt-get install ros-melodic-slam-gmapping`
3. `sudo apt-get install ros-melodic-amcl ros-melodic-map-server`


## CONFIGURATIONS

1. Export the robot type: `export TURTLEBOT3_MODEL=waffle`

(Note: You can change the model name with `burger` and `wafflepi` too)

2. Export the `GAZEBO_MODEL_PATH` with the directory in `turtlebot3_gazebo/models`: Assuming you are in workspace directory `export GAZEBO_MODEL_PATH=${GAZEBO_MODEL_PATH}:${pwd}/src/turtlebot3_gazebo/models`


To skip running these commands on each terminal, you can save these commands to `~/.bashrc` or `/opt/ros/melodic/setup,bash`


## PROCEDURE - SIMULATION

(Remember to source the workspace using: `source devel/setup.bash` from the workspace directory or copy the command to `~/.bashrc` or `/opt/ros/melodic/setup,bash`
)

1. You can start the simulation using `roslaunch turtlebot3_gazebo turtlebot3_world.launch` (Note: More environments are available in `turtlebot3_gazebo/worlds`)

## PROCEDURE - SLAM

1. To start autonomous slam, run

roslaunch turtlebot3_experimental turtlebot3_slam_autonomous.launch

2. To start the SLAM in manual mode, run `roslaunch turtlebot3_experimental turtlebot3_slam_manual.launch` and `roslaunch turtlebot3_experimental turtlebot3_teleop_key.launch`

3. To save the map, go to the directory of maps, run `rosrun map_server map_saver -f mymap`


## PROCEDURE FOR AMCL

1. To start the robot in the simulation, run

roslaunch turtlebot3_gazebo turtlebot3_world.launch

2. To start AMCL node, run

roslaunch turtlebot3_navigation turtlebot3_navigation.launch