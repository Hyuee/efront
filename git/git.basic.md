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
# 暂存已修改的文件
$ git add git/
```

![image-20200323204036513](git.basic.assets/image-20200323204036513.png)



## 将暂存区文件提交到本地仓库

```shell
# -m + 提交的信息
$ git commit -m "add git.basic.md"
# 跳过暂存区（提交所有修改的文件），直接提交
$ git commit -a -m 'add git.basic.md'
```

![image-20200323204746430](git.basic.assets/image-20200323204746430.png)



## 推送到远程仓库

```shell
# 第一次提交需要加上 --set-upstream
$ git push --set-upstream origin master
```

![image-20200323205341581](git.basic.assets/image-20200323205341581.png)

## 查看历史

```shell
$ git log
```

![image-20200323205603788](git.basic.assets/image-20200323205603788.png)



## 从远程仓抓取数据

```shell
$ git pull

remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 691 bytes | 2.00 KiB/s, done.
From https://github.com/Hyuee/efront
   fa8925c..aad3f5e  master     -> origin/master
Updating fa8925c..aad3f5e
Fast-forward
 test.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 test.md

# 查看文件列表
$ ls -l
total 2
drwxr-xr-x 1 14420 197609  0  3月 23 21:06 git/
-rw-r--r-- 1 14420 197609 30  3月 23 19:54 README.md
-rw-r--r-- 1 14420 197609 18  3月 23 21:02 test.md

```



## 修改文件

```shell
$ vim test.md

diff --git a/test.md b/test.md
index 307215a..1f4f845 100644
--- a/test.md
+++ b/test.md
@@ -1 +1,3 @@
 test pull command
+
+git diff HEAD
```

## 加入暂存区

```shell
14420@DESKTOP-UOORP2M MINGW64 /d/工作/实习/task/day200323/efront (master)
$ git add -A

14420@DESKTOP-UOORP2M MINGW64 /d/工作/实习/task/day200323/efront (master)
$ git status -s
A  git/git.basic.assets/image-20200323204036513.png
A  git/git.basic.assets/image-20200323204746430.png
A  git/git.basic.assets/image-20200323205341581.png
A  git/git.basic.assets/image-20200323205603788.png
M  git/git.basic.md
M  test.md
```

## 查看暂存区与本地库之间的差异

```shell
$ git diff --staged

diff --git a/git/git.basic.assets/image-20200323204036513.png b/git/git.basic.assets/image-20200323204036513.png
new file mode 100644
index 0000000..9220d16
Binary files /dev/null and b/git/git.basic.assets/image-20200323204036513.png differ
diff --git a/git/git.basic.assets/image-20200323204746430.png b/git/git.basic.assets/image-20200323204746430.png
new file mode 100644
index 0000000..c29b64b
Binary files /dev/null and b/git/git.basic.assets/image-20200323204746430.png differ
diff --git a/git/git.basic.assets/image-20200323205341581.png b/git/git.basic.assets/image-20200323205341581.png
new file mode 100644
index 0000000..a2015e9
Binary files /dev/null and b/git/git.basic.assets/image-20200323205341581.png differ
diff --git a/git/git.basic.assets/image-20200323205603788.png b/git/git.basic.assets/image-20200323205603788.png
new file mode 100644
index 0000000..4218a2b
Binary files /dev/null and b/git/git.basic.assets/image-20200323205603788.png differ
diff --git a/git/git.basic.md b/git/git.basic.md
index c62f6fb..a1f1183 100644
--- a/git/git.basic.md
+++ b/git/git.basic.md
```

## 重置暂存区中的文件

```shell
14420@DESKTOP-UOORP2M MINGW64 /d/工作/实习/task/day200323/efront (master)
# 重置 git目录下所有文件和test.md 
$ git reset git/ test.md
Unstaged changes after reset:
M       git/git.basic.md
M       test.md

14420@DESKTOP-UOORP2M MINGW64 /d/工作/实习/task/day200323/efront (master)
$ git status -s
M git/git.basic.md
M test.md
?? git/git.basic.assets/image-20200323204036513.png
?? git/git.basic.assets/image-20200323204746430.png
?? git/git.basic.assets/image-20200323205341581.png
?? git/git.basic.assets/image-20200323205603788.png
```

## 将工作区还原到修改之前

```shell
# 还原之前
$ git status -s
 M git/git.basic.md
 M test.md
?? git/git.basic.assets/image-20200323204036513.png
?? git/git.basic.assets/image-20200323204746430.png
?? git/git.basic.assets/image-20200323205341581.png
?? git/git.basic.assets/image-20200323205603788.png

14420@DESKTOP-UOORP2M MINGW64 /d/工作/实习/task/day200323/efront (master)
# 还原 test.md文件
$ git checkout -- test.md

14420@DESKTOP-UOORP2M MINGW64 /d/工作/实习/task/day200323/efront (master)
# 还原之后
$ git status -s
 M git/git.basic.md
?? git/git.basic.assets/image-20200323204036513.png
?? git/git.basic.assets/image-20200323204746430.png
?? git/git.basic.assets/image-20200323205341581.png
?? git/git.basic.assets/image-20200323205603788.png

```

## 创建新分支并切换到新分支

```shell
14420@DESKTOP-UOORP2M MINGW64 /d/工作/实习/task/day200323/efront (master)
# 创建分支
$ git branch dev

14420@DESKTOP-UOORP2M MINGW64 /d/工作/实习/task/day200323/efront (master)
# 切换到分支
$ git checkout dev
Switched to branch 'dev'
M       git/git.basic.md
```



## 推送到新分支

```shell
# 推送新分支到远程仓库
$ git push origin dev
Total 0 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/Hyuee/efront/pull/new/dev
remote:
To https://github.com/Hyuee/efront.git
 * [new branch]      dev -> dev
```

## 删除当前分支的文件

```shell
$ git rm 'test.md'
rm 'test.md'
```

## 提交修改到当前分支

```shell
$ git commit -m "remove test.md"
[dev 54e49fa] remove test.md
 1 file changed, 1 deletion(-)
 delete mode 100644 test.md
```

## 切换到master分支

```shell
$ git checkout master

Switched to branch 'master'
Your branch is up to date with 'origin/master'.
```

## 合并dev分支

```shell
$ git merge dev

Updating aad3f5e..3c497da
Fast-forward
 git/git.basic.assets/image-20200323204036513.png | Bin 0 -> 34769 bytes
 git/git.basic.assets/image-20200323204746430.png | Bin 0 -> 29272 bytes
 git/git.basic.assets/image-20200323205341581.png | Bin 0 -> 23847 bytes
 git/git.basic.assets/image-20200323205603788.png | Bin 0 -> 11025 bytes
 git/git.basic.md                                 | 218 +++++++++++++++++++++++
 test.md                                          |   1 -
 6 files changed, 218 insertions(+), 1 deletion(-)
 create mode 100644 git/git.basic.assets/image-20200323204036513.png
 create mode 100644 git/git.basic.assets/image-20200323204746430.png
 create mode 100644 git/git.basic.assets/image-20200323205341581.png
 create mode 100644 git/git.basic.assets/image-20200323205603788.png
 delete mode 100644 test.md
```

## 删除分支

```shell
# 删除本地分支（并没有删除远程dev分支）
$ git branch -d dev
Deleted branch dev (was 3c497da).

# 将删除操作push到远程仓
$ git push origin --delete dev

To https://github.com/Hyuee/efront.git
 - [deleted]         dev
```

## 回退

```shell
# 为了看到效果，先增加一个文件，并提交
$ vim testRevert1.md
# 加入暂存区
$ git add testRevert1.md
# 提交
$ git commit -m "add testRevert1.md"
[master 007bc01] add testRevert1.md
 1 file changed, 3 insertions(+)
 create mode 100644 git/testRevert1.md

# 回退一次
$ git revert HEAD
# 回退n次
$ git revert HEAD~n

Removing git/testRevert1.md
[master 33f4b8d] Revert "add testRevert1.md"
 1 file changed, 3 deletions(-)
 delete mode 100644 git/testRevert1.md
 
# 查看历史（简洁信息，只显示最新的2条）
$ git log --stat -2

commit 33f4b8d686fd4ecf1a1ff3fb5a1f4e26e69aaaf2 (HEAD -> master, origin/master, origin/HEAD)
Author: Hyuee <18623212546@139.com>
Date:   Tue Mar 24 09:37:17 2020 +0800

    Revert "add testRevert1.md"

    This reverts commit 007bc01991009e498db4719ec15f6c6c324f2601.

 git/testRevert1.md | 3 ---
 1 file changed, 3 deletions(-)

commit 007bc01991009e498db4719ec15f6c6c324f2601
Author: Hyuee <18623212546@139.com>
Date:   Tue Mar 24 09:36:19 2020 +0800

    add testRevert1.md

 git/testRevert1.md | 3 +++
 1 file changed, 3 insertions(+)
 

```

## 解决冲突

> 模拟冲突情况

```shell
# master中存在test.txt文件
$ ls -l

total 17
drwxr-xr-x 1 14420 197609     0  3月 24 08:37 git.basic.assets/
-rw-r--r-- 1 14420 197609 10077  3月 24 10:41 git.basic.md
-rw-r--r-- 1 14420 197609   115  3月 24 13:10 test.txt

# 创建并切换到新分支'feature1'
$ git checkout -b feature1
Switched to a new branch 'feature1'

# 在新分支中修改test.txt文件
$ vim test.txt

# 查看修改内容，+标识新增，可以看出‘worldffff’被替换成‘heyue’
$ git diff -b

diff --git a/git/test.txt b/git/test.txt
index dddbc0e..19748a9 100644
--- a/git/test.txt
+++ b/git/test.txt
@@ -2,6 +2,6 @@
 public class Animal
 {
     public static void main(String[] args){
-       System.out.println("Hello worldffff");
+       System.out.println("Hello heyue");
     }
 }

# 将修改提交到feature1分支
$ git commit -am 'update test.txt'

[feature1 5a84088] update test.txt
 1 file changed, 1 insertion(+), 1 deletion(-)

# 再切换到主分支
$ git checkout master

Switched to branch 'master'
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)
  
# 修改test.txt文件
$ vim test.txt

# 查看修改内容，可见增加了一行注释以及将“worldffff”替换成了“world”
$ git diff
diff --git a/git/test.txt b/git/test.txt
index dddbc0e..0439601 100644
--- a/git/test.txt
+++ b/git/test.txt
@@ -2,6 +2,7 @@
 public class Animal
 {
     public static void main(String[] args){
-       System.out.println("Hello worldffff");
+       // Say Hello
+       System.out.println("Hello world");
     }
}

# 将修改提交到主分支
$ git commit -am 'add comments'
[master 42b0be2] add comments
 1 file changed, 2 insertions(+), 1 deletion(-)

# 最后合并，合并时出现了“CONFLICT (content): Merge conflict in git/test.txt”
# 并且“Automatic merge failed”，自动合并失败，这时需要手动合并。
$ git merge feature1
Auto-merging git/test.txt
CONFLICT (content): Merge conflict in git/test.txt
Automatic merge failed; fix conflicts and then commit the result.

# 打开文件进行手动合并冲突
$ vim test.txt
# 最终合并为
public class Animal
{
    public static void main(String[] args){
        // Say Hello
        System.out.println("Hello world");
        // Solve Conflicts
        System.out.println("Hello heyue");
    }
}

# 提交修改
$ git commit -am "Solve Conflicts"
[master 9914311] Solve Conflicts

# 冲突已解决
$ git status
On branch master
Your branch is ahead of 'origin/master' by 7 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

