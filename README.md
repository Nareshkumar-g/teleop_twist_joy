# teleop_twist_joy
teleop_twist_joy_ws is to modify the joy and teleop_twist_joy package.

# First uninstall the teleop_twist_joy package from ROS
 sudo apt-get remove ros-humble-teleop-twist-joy

# Clone it locally
https://github.com/ros2/teleop_twist_joy/tree/foxy - Change the branch name accordingly

# Then modify the teleop_twist_joy package - Go to src and open teleop_twist_joy.cpp 

Comment the below lines - WHich is responsible to produce zero velocity

  // else
  // {
  //   // When enable button is released, immediately send a single no-motion command
  //   // in order to stop the robot.
  //   if (!sent_disable_msg)
  //   {
  //     // Initializes with zeros by default.
  //     auto cmd_vel_msg = std::make_unique<geometry_msgs::msg::Twist>();
  //     cmd_vel_pub->publish(std::move(cmd_vel_msg));
  //     sent_disable_msg = true;
  //   }
  // }

  # Then go to launch dir and teleop-launch.py

  Increase the "autorepeat_rate"

