## Fabric开发环境配置 ##

### 1. 系统环境配置 ###

- **1.1 设置root用户**	<br> 	
sudo passwd 

- **1.2 安装git**		<br>
apt-get install git

- **1.3 安装vim**	    <br>
apt-get install vim

- **1.4 安装openssh**	<br>
apt-get install openssh-server <br> 
sudo vi /etc/ssh/sshd_conf     <br> 
modify PermitRootLogin:prohibit-password to PermitRootLogin:yes<br> 
service ssh restart	

- **1.5 安装curl工具**	<br>
apt-get install curl

- **1.6 安装jq** 		<br>
apt-get install jq

- **1.7 安装python**     <br>
apt-get install python



### 2. 开发环境配置 ###
- **2.1 docker相关组件的安装**<br>
apt-get install docker.io<br>
apt-get install docker-compose

- **2.2 go语言环境的安装**	<br>
wget https://storage.googleapis.com/golang/go1.8.3.linux-amd64.tar.gz<br>
tar -xvf go1.8.3.linux-amd64.tar.gz<br>
mv go /usr/local<br>
sudo chown -R root:root /usr/local/go<br>
mkdir -p /opt/goworkspace/src<br>
mkdir -p /opt/goworkspace/bin<br>
mkdir -p /opt/goworkspace/pkg<br>
sudo vim /etc/profile<br>
**添加如下内容**<br>
export GOROOT=/usr/local/go<br>
export GOPATH=/opt/goworkspace<br>
export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin<br>
**执行**<br>
source /etc/profile

- **2.3 nodejs环境的安装** 	<br>
wget https://nodejs.org/dist/v6.9.5/node-v6.9.5-linux-x64.tar.xz<br>
xz -d node-v6.9.5-linux-x64.tar.xz<br>
tar -xvf node-v6.9.5-linux-x64.tar<br>
mv node-v6.9.5-linux-x64 node<br>
sudo mv node /usr/local<br>
sudo chown -R root:root /usr/local/node<br>
sudo vi /etc/profile<br>
**添加如下内容**<br>
export PATH=$PATH:/usr/local/node/bin<br>
**执行**<br>
source /etc/profile<br>
