
```shell
git clone https://github.com/dusty-nv/jetson-containers.git
wget https://vision.in.tum.de/rgbd/dataset/freiburg2/rgbd_dataset_freiburg2_pioneer_slam2.tgz -O /home/nx/datasets/
cd jetson-containers
./scripts/docker_run.sh -c dustynv/ros:foxy-slam-l4t-r32.5.0  --volume /home/nx/datasets/:/datasets
```

Inside the docker container:
```
cd /opt/ORB_SLAM2_CUDA
./build/mono_tum Vocabulary/ORBvoc.txt Examples/Monocular/TUM2.yaml /datasets/rgbd_dataset_freiburg2_pioneer_slam2/ true
```
