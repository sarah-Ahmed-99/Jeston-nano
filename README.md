# Jeston-nano
Here are the steps to install ROS (Robot Operating System) on a Jetson Nano:
Here are the steps to install ROS (Robot Operating System) on a Jetson Nano:

## 1. Set up the Jetson Nano hardware:
   - Download the Jetson Nano Developer Kit image from the NVIDIA website.
   - Flash the image onto a microSD card and insert it into the Jetson Nano.
   - Power on the Jetson Nano and complete the initial setup.

## 2. Install ROS Melodic on Ubuntu 18.04:
  -  Open a terminal on the Jetson Nano and add the ROS repository to the system's sources list:
    
        ` sudo sh -c echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list`
   - Set up the keys:

       `  sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654`
   - Install ROS Melodic:
     
        ` sudo apt update
        sudo apt install ros-melodic-desktop-full`

  -  Initialize the ROS environment:
       
       ` source /opt/ros/melodic/setup.bash`
     
## 3. Install additional ROS dependencies:
   - Install common ROS dependencies:
     
      ` sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential`
   - Initialize rosdep:
     
        ` sudo rosdep init
         rosdep update`
     
## 4. Create a ROS workspace:
  - Create a catkin workspace:
    
       `  mkdir -p ~/catkin_ws/src
     cd ~/catkin_ws
     catkin_make`
    
  - Source the workspace setup file:
       
    `source devel/setup.bash`
     
## 5. Test the ROS installation:
   - Run the ROS core:

        ` roscore`
  - In a new terminal, run the ROS talker and listener nodes:
          
    `rosrun beginner_tutorials talker.py
         rosrun beginner_tutorials listener.py`
  - You should see the talker node publishing messages and the listener node receiving and printing them.

    This covers the basic steps to install ROS Melodic on a Jetson Nano running Ubuntu 18.04. You can now proceed with developing and running ROS applications on your Jetson Nano.
