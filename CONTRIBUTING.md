## 贡献指南


### Go
GO需要写在Go上。如果没有GO开发环境，请设置一个。<br>
GO的版本应为1.11或以上。<br>
安装之后，需要定义GOPATH，并修改PATH以访问Go二进制文件。<br>
一个常见的设置如下，您可以根据自己的喜好设置。<br>
```Go
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
```
## 工作流


### 第1步：fork远程仓库
1、访问HTTPS:/GIHUUBCOM/GO-JVM/GOJVM <br>
2、点击Fork按钮（右上）建立基于fork的远程仓库。<br> 
### 第2步：克隆仓库到本地存储 
定义本地工作目录：
```Go
# If your GOPATH has multiple paths, pick
# just one and use it instead of $GOPATH here.
working_dir=$GOPATH/src/github.com/gojvm
```
创建克隆： 
```Go
mkdir -p $working_dir
cd $working_dir
git clone https://github.com/$user/gojvm.git
# the following is recommended
# or: git clone git@github.com:$user/gojvm.git
```
```Go
cd $working_dir/tidb
git remote add upstream https://github.com/go-jvm/gojvm.git
# or: git remote add upstream git@github.com:go-jvm/gojvm.git
```
```Go
# Never push to upstream master since you do not have write access.
git remote set-url --push upstream no_push
```
```Go
# Confirm that your remotes make sense:
# It should look like:
# origin    git@github.com:$(user)/gojvm.git (fetch)
# origin    git@github.com:$(user)/gojvm.git (push)
# upstream  https://github.com/go-jvm/gojvm.git (fetch)
# upstream  no_push (push)
git remote -v`
```
### 第3步：分支 
本地动态:
```Go
cd $working_dir/gojvm
git fetch upstream
git checkout master
```
```Go
git rebase upstream/master
```
主分支： 
```Go
git checkout -b myfeature
```
### 第4步:开发
##### 编辑代码

##### 运行测试

### 第5步：保持分支同步 
```Go
# While on your myfeature branch.
git fetch upstream
git rebase upstream/master
```
### 第6步：提交
提交更改
```Go
git commit
```
### 第7步：push 

当准备复查时（或者只是为了建立离线备份或者工作），将分支推到您的分支上 github.com:

```Go
git push -f origin myfeature
```
### 第8步：创建拉动请求 

1、在http://gthub.com /$用户/Gojvm（替换$$）访问您的仓库。<br>

2、单击MyStices分支旁边的比较和拉取请求按钮。 
### 第9步：获得代码复查 
