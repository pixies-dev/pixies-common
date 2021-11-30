
# Pixies <package-name>

<p align="center">
  <img src="https://static.wixstatic.com/media/252a39_be40c5f0d1b7452d8be12f18259044bd~mv2.png/v1/crop/x_0,y_315,w_1600,h_500/fill/w_497,h_148,al_c,q_85,usm_0.66_1.00_0.01/Logo_Pixies.webp" width="500" title="logo">
</p>

## Overview

Describe here what this package does and what it's meant for in a few sentences.

**Author: yourname<br />
Affiliation: [PixiesUrbanLab](https://www.pixiesurbanlab.com/)<br />
Maintainer: yourname, youremail**

The PACKAGE NAME package has been tested under [ROS] Indigo, Melodic and Noetic on respectively Ubuntu 14.04, 18.04 and 20.04.

## Installation

### Installation from Packages

To install all packages from the this repository as Debian packages use

    sudo apt-get install ros-noetic-...
    
Or better, use `rosdep`:

	sudo rosdep install --from-paths src

### Building from Source

#### Dependencies

- [Robot Operating System (ROS)](http://wiki.ros.org) (middleware for robotics),
- [Eigen] (linear algebra library)

	sudo rosdep install --from-paths src
- All the dependencies you need...

#### Building (in case you need)

To build from source, clone the latest version from this repository into your catkin workspace and compile the package using

	cd catkin_workspace/src
	git clone https://github.com/ethz-asl/ros_best_practices.git
	cd ../
	rosdep install --from-paths . --ignore-src
	catkin_make

### Running in Docker (in case you need)

Docker is a great way to run an application with all dependencies and libraries bundles together. 
Make sure to [install Docker](https://docs.docker.com/get-docker/) first. 

First, spin up a simple container:

	docker run -ti --rm --name ros-container ros:noetic bash
	
This downloads the `ros:noetic` image from the Docker Hub, indicates that it requires an interactive terminal (`-t, -i`), gives it a name (`--name`), removes it after you exit the container (`--rm`) and runs a command (`bash`).

Now, create a catkin workspace, clone the package, build it, done!

	apt-get update && apt-get install -y git
	mkdir -p /ws/src && cd /ws/src
	git clone https://github.com/leggedrobotics/ros_best_practices.git
	cd ..
	rosdep install --from-path src
	catkin_make
	source devel/setup.bash
	roslaunch ros_package_template ros_package_template.launch

## Usage

Describe the quickest way to run this software, for example:

Run the main node with

	roslaunch ros_package_template ros_package_template.launch

## Config files

Config file folder/set 1

* **config_file_1.yaml** Shortly explain the content of this config file

Config file folder/set 2

* **...**

## Launch files

* **launch_file_1.launch:** shortly explain what is launched (e.g standard simulation, simulation with gdb,...)

     Argument set 1

     - **`argument_1`** Short description (e.g. as commented in launch file). Default: `default_value`.

    Argument set 2

    - **`...`**

* **...**

## Nodes

### ros_package_template

Reads temperature measurements and computed the average.


#### Subscribed Topics

* **`/temperature`** ([sensor_msgs/Temperature])

	The temperature measurements from which the average is computed.


#### Published Topics

...


#### Services

* **`get_average`** ([std_srvs/Trigger])

	Returns information about the current average. For example, you can trigger the computation from the console with

		rosservice call /ros_package_template/get_average


#### Parameters

* **`subscriber_topic`** (string, default: "/temperature")

	The name of the input topic.

* **`cache_size`** (int, default: 200, min: 0, max: 1000)

	The size of the cache.


### NODE_B_NAME

...


## Bugs & Feature encountered
List here known bugs, how you solved them and also those not fixed yet

