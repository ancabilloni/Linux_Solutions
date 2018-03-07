*This document shows steps for a method to install ROS on a system with existing Conda.* 
*The following steps were tested on ROS Kinetic and Miniconda3 on Ubuntu 16.04*

### Understand the conflict with Python between ROS and Conda:
- Ubuntu 16.04 has Python 2.7 by default.
- Current ROS Kinetic supports up to Python 2.7 on Ubuntu 16.04.
- Conda installation with Python 3 by default, and will set Python path automatically to Python 3 for the system.
While installing ROS itself on a Conda existing machine may not have any problem, there will be incompability issues when trying to install Python packages or run Python script meant for ROS on a Conda existing machine.

### Solution:
**Step 1:** Test current Python version.

Start new Terminal > type `python` > record which version it is > If the current version is Python 3, then we need to switch it to 2.7 default

**Step 2:** Comment Conda path in `bashrc` file to return Ubuntu Python default back to 2.7.

Start new Terminal > type `gedit ~/.bahsrc` > Scroll to end of the page to find the conda path and comment it > Save `bashrc` > Close Terminal

Example:

![selection_091](https://user-images.githubusercontent.com/23693651/37070592-2f7a0272-2186-11e8-8520-2f701fb0a499.png)

**Step 3:** Repeat step 1 to check if you have Python 2.7

**Step 4:** Go to ROS official installation website, and install ROS: http://wiki.ros.org/kinetic/Installation/Ubuntu

### To use Conda:

- Repeat step 2 above and uncomment Conda path.

### In other case for an existing ROS installed machine and try to install Conda.
See this post https://github.com/udacity/RoboND-Python-StarterKit/blob/master/doc/linux_ros_anaconda_warning.md

