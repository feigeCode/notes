# 部署spingboot

## 部署springboot项目的两种方式

### 第一种：war包

去官网下载Tomcat，通过winscp或xftp把压缩包上传到服务器，解压

~~~bash
启动命令 
sh startup.sh
关闭命令
sh shutdown.sh
~~~

访问ip:端口如果出现Tomcat的一个页面就成功了

把springboot的war包放在webapps目录下

通过ip:端口/项目名称/首页

如果成功测显示首页

### 第二种：jar包

~~~bash
java -jar ./项目名字
# 后台运行
nohup java -jar xiaofei-cloud-classroom-api-1.0-SNAPSHOT.jar > xiaofei.log &
~~~

## 项目在Linux启动正常，但不能访问

#### 我们可以通过多种方式进行一一排除，排查出原因：

#### 第一种：通过浏览器访问，但不显示，这是最直观的验证项目是否已经运行的方式，本质上其实就是外网的访问；

#### 第二种：在linux服务器上，通过命令进行验证，如果无法访问，则不显示任何东西；

如果访问正常，会显示出项目首页的前端代码

~~~bash
curl http://localhost:端口/
~~~



#### 第三种：通过命令看防火墙是否开启，有打印出内容说明有开启

~~~ba
netstat -aptn | grep -i 端口
~~~



#### 第四种：验证外网端口是否开启

PS：需要注意的是，第四种情况，是针对云服务器而言的，一般的云服务器，都会另外针对服务器，加多了一层防火墙。所以如果没有进行开启，同样也是会导致无法连接；

下边是开启步骤：

![image-20200216222953874](https://gitee.com/feigeCode/picture/raw/master/img/image-20200216222953874-1601786067617.png)x

![image-20200216223050452](https://gitee.com/feigeCode/picture/raw/master/img/image-20200216223050452.png)

