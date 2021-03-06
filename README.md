## Intro

Source code for the paper: Terrain-Adaptive Locomotion Skills using Deep Reinforcement Learning
https://www.cs.ubc.ca/~van/papers/2016-TOG-deepRL/index.html

## Setup

This section covers some of the steps to setup and compile the code. The software depends on many libraries that need to be carefully prepared and placed for the building and linking to work properly.

### Linux

 1. Caffe (http://caffe.berkeleyvision.org/installation.html)  
	Specific version (https://github.com/niuzhiheng/caffe.git @ 7b3e6f2341fe7374243ee0126f5cad1fa1e44e14)
	sudo apt-get install libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler  
	sudo apt-get install --no-install-recommends libboost-all-dev  
	sudo apt-get install libgflags-dev libgoogle-glog-dev liblmdb-dev  
	sudo apt-get install libatlas-base-dev  
	
	In the instruction to make and build Caffe uncomment the CPU only line  
	```
	# CPU-only switch (uncomment to build without GPU support).
	CPU_ONLY := 1
	```

	Or if on Windows  
	https://github.com/initialneil/caffe-vs2013

 2. Boost  
 3. OpenCV  
 4. BulletPhysics
 5. CUDA  
	Package Manager Installation  
	Install repository meta-data  
	When using a proxy server with aptitude, ensure that wget is set up to use the	same proxy settings before installing the cuda-repo package.  
	$ sudo dpkg -i cuda-repo-<distro>_<version>_<architecture>.deb  
	Update the Apt repository cache  
	$ sudo apt-get update  
	Install CUDA  
	$ sudo apt-get install cuda  
 	
 6. Json_cpp (https://github.com/open-source-parsers/jsoncpp)  
 7. Eigen (http://eigen.tuxfamily.org/index.php?title=Main_Page)  
 8. bits  
	sudo apt-get install gcc-4.9-multilib g++-4.9-multilib 
11. LodePNG  
 	https://github.com/lvandeve/lodepng


### Windows

## Runing The System

After the system has been build there are two executable files that server different purposes. The **TerrainRL** program is for visually simulating the a controller and **TerrainRL_Optimize** is for optimizing the parameters of some controller.

Examples:  
	To simulate a controller/character  
	./TerrainRL -arg_file= args/sim_dog_args.txt  
	To simulate a controller/character with a specific policy  
	./TerrainRL_Optimizer -arg_file= args/dog_slopes_mixed_args.txt
	To Train a controller  
	./TerrainRL_Optimizer -arg_file= args/opt_args_train_mace.txt  


## Key Bindings

Most of these are togglesg

 - c fixed camera mode
 - y draw COM path and contact locations
 - q draw "filmstrip" like rendering
 - f draw torques
 - h draw Actor value functions and feature visualization
 - shift + '>' step one frame
 - p toggle draw value function
 - ',' and '.' change render speed, decrease and increase.
 - "spacebar" to pause simulation
 - r restart the scenario
 - l reload the simulation (reparses the arg file)
 - g draw state features
 - x spawn projectile
 - z spawn big projectile
 
 - click on character and drag to apply force
