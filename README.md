# fabric-env
build fabric env step by step

notice:
madison和policy是apt-cache子命令，可以通过man apt-cache查询更多用法。
apt-cache madison <<package name>>
将列出所有来源的版本。
apt-cache policy <<package name>>
将列出所有来源的版本。信息会比上面详细一点

1,extra tools
vim 
command : apt-get install vim

openssh
command : apt-get install openssh-server
then    : 
  sudo vi /etc/ssh/sshd_conf    ---> modify PermitRootLogin:prohibit-password  to PermitRootLogin:yes
finally : service ssh restart

python
command : apt install python-pip

2,fabric environment needed
docker
command : apt-get install docker.io

docker-compose
command : apt-get install docker-compose

nodejs
command : export PATH=$PATH:/usr/local/node/bin
then : 
  extract
    xz -d node-v6.9.5-linux-x64.tar.xz
    tar -xvf node-v6.9.5-linux-x64.tar
  rename 
    mv node-v6.9.5-linux-x64 node
finally : 
  add to system env
    vim /etc/profile
  add this line on the top of file.
    export PATH=$PATH:/usr/local/node/bin

golang
command : wget https://storage.googleapis.com/golang/go1.8.3.linux-amd64.tar.gz
then
  extract:
    tar -xvf go1.8.3.linux-amd64.tar.gz
finally:
   add to system env
      vim /etc/profile
   add this line on the top of file.
      export GOROOT=/home/randy/go
      export GOPATH=/home/randy/mygo
      export PATH=$PATH:$GOROOT/bin
   create three directories for gopath
      cd myfo
      mkdir pkg
      mkdir bin
      mkdir src
