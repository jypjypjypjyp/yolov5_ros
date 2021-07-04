## Ros Requirement
**ROS Noetic**


## Clone and Install requirement
```bash
mkdir -p catkin_ws_pytorch_yolov5/src
cd catkin_ws_pytorch_yolov5/src
git clone https://github.com/Shua-Kang/yolov5.git

# If pytorch gpu is needed, install pytorch with gpu firstly. See https://pytorch.org/get-started/locally/
# Upgrade pip and install requirement
cd yolov5/src/yolov5/
python3 -m pip install --upgrade pip
pip3 install -r requirements.txt
```

### Build yolov5 pytorch
```bash
cd catkin_ws_pytorch_yolov5
catkin init
catkin build
```

## Start

### Launch yolov5_torch Node in One Terminal
```bash
cd catkin_ws_pytorch_yolov5
source devel/setup.bash
roslaunch yolov5_torch detector.launch device:=cpu
#or launch with gpu device 0
roslaunch yolov5_torch detector.launch device:=0
# multi-gpu: roslaunch yolov5_torch detector.launch device:=0,1
```

### Rosbag Play in Another Terminal
```bash
cd catkin_ws_pytorch_yolov5
source devel/setup.bash
cd src/yolov5/bag_dataset
rosbag play test_yolo.bag
```
