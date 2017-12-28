# 常见的问题与注意事项
### ROS安装与配置的注意事项
#### 安装
* Q1：安装过程必须严格按照官网或者本教程给出的步骤执行，不然可能会出现各种未知问题。
* Q2：安装第一步的添加镜像源，如果遇到网关访问不了官网的源，推荐使用本教程中科大的镜像源。
* Q3：安装的ROS版本和Linux版本有什么特殊要求？

 A3：必须是版本相对应的，不然会出现各种未知版本不兼容问题。 
* Q4：安装过程出现`unmet dependency`错误，是怎么回事?

 A4: 是软件包安装的依赖问题。触发原因有可能是误删操作，也有可能是ROS版本不兼容，解决办法手动添加依赖或者重装ROS。
* Q5: 安装过程出现`hash sum mismatch`？

   A5：触发原因可能是意外退出更新过程，解决办法重新更新。
 
#### 配置
* Q6：在安装完ROS之后，首先要配置ROS环境，很重要的一步 `$ echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc`，这句的作用是每次打开终端系统自动添加ROS环境。

### ROS操作过程问题与注意事项
* Q7：从GitHub上下载源代码的时候，要注意有些依赖本身系统并没有安装配置，怎么解决？

  A7:回到工作空间手动添加依赖，命令如下：
  
             $ cd ~/catkin_ws
             $ rosdep install --from-paths src --ignore-src --rosdistro=kinetic -y
             
* Q8：编译完自己的程序，怎么样让系统找到我们自己所编写的程序包？

  A8:执行语句：`source ~/catkin_ws/devel/setup.bash`,
  
* Q9：Q8这句命令生命周期很短，只在目前的终端有效，怎么解决？
  A9：将上述命令写入.bashrc文件中，执行命令`echo "source ~/catkin_ws/devel/setup.bash">> ~/.bashrc`即可解决。
