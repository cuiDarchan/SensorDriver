# 传感器驱动
主要收藏和修改各种自动驾驶和智能化相关的各类驱动程序，方便随时取用。
<br/>

# 包含内容
## 1. livox_ros_driver
大疆激光雷达的驱动程序，基于官方的SDK开发的。    
1）新增了自定义指定多激光topic和imu的topic

## 2. hikision_ros
海康威视的相机驱动ROS版本，基于官方的SDK开发的。  
1）新增一些必要的流程性中文注释。
*注意：* 海康威视与海康机器人工业相机是有区别的，请拿到设备后注意甄别型号

## 3. hikrobot_camera
海康机器人的相机驱动ROS版本，基于官方的SDK开发的。  
1）临时去掉一些无法编译通过的链接库。  
2）需要[参考](https://blog.csdn.net/weixin_41965898/article/details/116801491)安装MVS工具，否则
*注意：* 海康威视与海康机器人工业相机是有区别的，请拿到设备后注意甄别型号

# 使用教程
新建一个ros的工作空间，将这些驱动包放入其中,编译即可
```
mkdir -p sensor_driver_ws
cd sensor_driver_ws
mkdir -p src
cd src
git clone xx.git
catkin_make -DCATKIN_WHITELIST_PACKAGES="livox_ros_driver;hikvision_ros" # 只编译臂头感知项目所需的安装包
```
注意： 只使用catkin_make 会默认安装hikrobot_camera，可能回报头文件错误，因没有安装MVS工具