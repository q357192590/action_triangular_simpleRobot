# action_triangular_simpleRobot
  
## 启动流程:  
0.先插底盘usb，再插xsense（双排usb插下方）  
1.sudo chmod 777 /dev/ttyUSB0  
2.sudo chmod 777 /dev/ttyUSB1  
3.复位定位系统，通过reset按钮  
4.roslaunch serial_communication start.launch  
  
## tips:  
1.雷达数据需要修改ip地址，具体看lidar数据手册  
2.车轮上电不锁，可能can连线问题及主控can芯片问题  
3.nuc与stm32需要串口转usb连接才能上传定位系统数据及通过键盘控制底盘,连接方式红黑绿白  
4.NoMachine连接的时候必须处于同一网段，即aaa.bbb.ccc.xxx  
  
## dependence:  
1.PCL  
2.gtsam  
