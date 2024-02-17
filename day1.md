# ROS命令

## 1.增加

catkin_create_pkg 自定义包名 依赖包 === 创建新的ROS功能包

sudo apt install xxx === 安装 ROS功能包

## 2.删除

sudo apt purge xxx  ==== 删除某个功能包

rospack find 包名 === 查找某个功能包是否存在，如果存在返回安装路径

roscd 包名 === 进入某个功能包

rosls 包名 === 列出某个包下的文件

apt search xxx === 搜索某个功能包

## 3.查找

rospack list === 列出所有功能包

## 4.修改

rosed 包名 文件名 === 修改功能包文件

需要安装 vim

**比如:**rosed turtlesim Color.msg

## 5.执行

### 5.1 roscore

**roscore ===** 是 ROS 的系统先决条件节点和程序的集合， 必须运行 roscore 才能使 ROS 节点进行通信。

roscore将启动：

- ros master
- ros 参数服务器
- rosout 日志节点



### 5.2 rosrun

**rosrun 包名 可执行文件名**  === 运行指定的ROS节点

**比如:**`rosrun turtlesim turtlesim_node`



### 5.3 roslaunch

**roslaunch 包名 launch文件名** === 执行某个包下的 launch 文件





# 话题通信

## 模型

### 角色

1.master --->管理者（媒婆）

2.talker   --->发布者（男方）

3.listener --->订阅者（女方）

### 流程

master可以根据话题建立发布者与订阅者之间的连接

### 注意

1.使用的协议有RPC和TCP；

2.步骤0和步骤1没有顺序关系

3.talker和listener都可以存在多个

4.talker和listener建立连接以后，master就可以关闭了

5.上述实现流程以及封装好了，以后直接调用即可
