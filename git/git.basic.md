# Git基础练习

## 全局设置
> 查看所有配置
```shell
git config --list
```
![image-20200323193309409](git.basic.assets/image-20200323193309409.png)



> 查看单个配置项
```shell
$ git config user.name
```

![image-20200323194714067](git.basic.assets/image-20200323194714067.png)



> 全局配置

```shell
$ git config --global user.name "Hyuee"
$ git config --global user.email 18623212546@139.com
$ git config --global credential.helper store
$ git config --global core.autocrlf false
```

## 克隆远程仓库

```shell
# 克隆远程项目（名称默认为远程仓库名）
$ git clone https://github.com/Hyuee/efront.git
# 克隆远程项目（自定义克隆后的名称为demo）
$ git clone https://github.com/Hyuee/efront.git demo
```
![image-20200323195516201](git.basic.assets/image-20200323195516201.png)

## 查看状态

```shell
$ git status
```

![image-20200323200023209](git.basic.assets/image-20200323200023209.png)

## 文件操作

```shell
# 创建文件夹
$ mkdir git
# 列出当前目录下的文件
$ ls -l
# 切换目录
$ cd git
# 复制文件或目录 + 目标目录（-i若目标档已经存在时，在覆盖时会先询问）
$ cp -i git.basic.md git
# 移除文件或者目录
$ rm git.basic.md git
# 移动文件或者目录
$ mv -i git.basic.md git
# 编辑文件, i键插入，esc :wq 保存退出
$ vim git.basic.md
```

![image-20200323201825141](git.basic.assets/image-20200323201825141.png)

## 再次查看状态

```shell
# 查看详细状态
$ git status
# 查看简洁状态信息
$ git status -s
```

![image-20200323203834551](git.basic.assets/image-20200323203834551.png)

## 将文件添加到暂存区

```shell

```
