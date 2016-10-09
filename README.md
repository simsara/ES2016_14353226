# DOL开发环境配置
###### *==说明：由于上次实验只截图了最后配置成功的页面，所以前面的截图是借同学的图或者PPT中的图来展示中间效果==*
## ○Description(DOL框架描述)
## ○How to install(DOL安装笔记)
#### 1.安装一些必要的环境(ubuntu)
1. **$ sudo apt-get update**  
![1](http://i.imgur.com/yU4eDQD.png)
2. **$ sudo apt-get install ant**
![2](http://i.imgur.com/3zQtHxn.png)
3. **$ sudo apt-get install openjdk-7-jdk**
![3](http://i.imgur.com/u8N2gGt.png)
4. **$ sudo apt-get install unzip**
![4](http://i.imgur.com/oXCADnL.png)

#### 2.下载文件(从主机粘贴到虚拟机)
1. 新建dol文件夹：**$  mkdir dol**
2. 将dolethz.zip解压到 dol文件夹中：**$  unzip dol_ethz.zip -d dol**
![5](http://i.imgur.com/1IHapsP.png)
3. 解压systemc：**$   tar -zxvf systemc-2.3.1.tgz**
![6](http://i.imgur.com/8O9e7et.png)
![7](http://i.imgur.com/mvzg6n4.png) 
#### 3.编译systemc
1. 解压后进入systemc-2.3.1的目录下：
**$   cd systemc-2.3.1**
2. 新建一个临时文件夹objdir：**$  mkdir objdir**
3. 进入该文件夹objdir：**$	cd objdir**
4. 运行configure(能根据系统的环境设置一下参数，用于编译)：**$	../configure CXX=g++ --disable-async-updates**
![8](http://i.imgur.com/zgj1Lm2.png)
下图为运行完之后的截图：
![9](http://i.imgur.com/sucIuDQ.png)
5. 编译：**$	sudo make install**(编译完后文件目录如下($ cd ..$ ls
![10](http://i.imgur.com/53InMhw.png) 
6. 记录当前的工作路径(会输出当前所在路径，记下来，待会有用)：**$	pwd**
![11](http://i.imgur.com/pnqbDm9.png)

#### 4.编译dol
1. 进入刚刚dol的文件夹:**$	cd ../dol**
2. 修改build_zip.xml文件,找到下面这段话，就是说上面编译的systemc位置在哪里:<property name="systemc.inc" value="YYY/include"/>
<property name="systemc.lib" value="YY,然后是编译:
**$	ant -f build_zip.xml all**,
若成功会显示build successful
![12](http://i.imgur.com/EBFxhXE.png)  
![13](http://i.imgur.com/LhHFNVu.png)  
![14](http://i.imgur.com/H2o2V5A.png)
![15](http://i.imgur.com/ETweaHl.png) 
3. 接着可以试试运行第一个例子,
进入build/bin/mian路径下:
**$	cd build/bin/main**
然后运行第一个例子:
**$	ant -f runexample.xml -Dnumber=1**,成功结果如图
![16](http://i.imgur.com/VCXWYbq.png) 
#### 5.Run example1：
1. **$ cd build/bin/main**
2. **$ ant -f runexample.xml -Dnumber=1**

## ○Experimental
experience(实验感想、实验心得)
****