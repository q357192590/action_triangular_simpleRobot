# action_triangular_simpleRobot
  
## 启动流程:  
0.先插底盘usb，再插xsense（双排usb插下方）  
1.sudo chmod 777 /dev/ttyUSB0  
2.sudo chmod 777 /dev/ttyUSB1  
3.roslaunch serial_communication start.launch
4.Caps调整速度
5.复位定位系统，通过reset按钮  
6.roslaunch lego_loam run.launch
(7.)录制bag:rosbag record -a

## tips:  
1.雷达数据需要修改ip地址，具体看lidar数据手册  
2.车轮上电不锁，可能can连线问题及主控can芯片问题  
3.nuc与stm32需要串口转usb连接才能上传定位系统数据及通过键盘控制底盘,连接方式红黑绿白  
4.NoMachine连接的时候必须处于同一网段，即aaa.bbb.ccc.xxx  
5.输出地图代码位于mapOptmization.cpp -> visualizeGlobalMapThread(),其中参数fileDirectory位于utility.h文件中，需要提前修改保存路径或创建文件夹，否则结束时报PCDSaveIOException。查看方法:pcl_viewer xxx.pcd
6.分析软件evo：画轨迹图：evo_traj bag 2022-04-03-18-05-16.bag --all_topic -p --plot_mode=xz
  
## dependence:  
1.PCL  
2.gtsam  
3.d435
