# quadrotor_landing
Autonomous Quadrotor landing on a moving platform

System Setup:
1. Install Ardrone Driver from the below link <br /> 
   https://ardrone-autonomy.readthedocs.io/en/latest/installation.html
   
2. Clone this repository in workspace
3. Run below commands in the workspace directory <br />
   catkin_make <br />
   source devel/setup.bash <br />
   roslaunch takeoff both.launch <br />
   
4. open a new terminal and run below commands <br />
    source devel/setup.bash <br />
    roslaunch uav_vision detection_tracking.launch <br />
    
5. open a new terminal and run below commands <br />
    source devel/setup.bash <br />
    rostopic pub /ardrone/takeoff std/msgs "{}" <br />
    
