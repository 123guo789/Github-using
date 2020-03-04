# GitHub使用手册

## 1、基本概念

+ 仓库（Repository）:仓库用来存放项目代码，每个项目对应一个仓库，多个开源项目则有多个项目。

+ 收藏（Star）
+ 复制克隆项目（Fork）:该Fork的项目是独立

+ 发起请求（Pull Request）
+ 关注（Watch）
+ 事物卡片（Issue）：发现代码bug，但是没有成型代码，需要讨论用

快捷键(t)：快速查找仓库文件

## 2、开源项目贡献流程

+ 新建Issue：提交使用问题或者建议或者想法
+ Pull Request

步骤：

1. fork项目
2. 修改自己仓库的项目代码
3. 新建pull request
4. 等待作者操作（合并）

## 3.Git安装和使用

**目的**：使用git管理github托管项目代码

**官方下载网址**https://git-scm.com/download/win

安装都是默认设置，除了下图

![install.png](https://github.com/123guo789/-Git/blob/master/images/install.png?raw=true)

**检验是否安装成功**：右击鼠标显示`Git GUI Here`和`Git Bash Here`

### 1、Git工作区域

1. Git Repository（Git仓库）最终确定的文件保存到仓库，成为一个新的版本，并对他人可见
2. 暂存区 暂存已经修改的文件最后统一提交到Git仓库中
3. 工作区（Working Directory）添加、编辑、修改文件等动作

### 2、Git的基本设置

#### 1、设置用户名

```
git config –-global user.name '这里填写自己的用户名'
```

#### 2、设置邮箱

```
git config –-global user.email '这里填写自己的用户名邮箱'
```

#### 3、一些需要记住的命令

+ git status：确定当前文件所处Git工作区域

假设在工作区有文件111.txt

1、工作区转入暂存区

~~~
git add 111.txt
~~~

2、暂存区转入Git仓库

~~~
git commit -m '提交描述'
~~~

3、确认文件是否已经在仓库中

~~~
git status
~~~

4、删除工作区文件

~~~
git rm -f 文件名
~~~

5、修改文件

~~~
vi 文件名
~~~

退出使用wq

### 3、初始化一个新的Git仓库

1. 创建文件夹
2. 在文件夹内初始化Git（创建Git 仓库）命令行进入当前目录，使用 `git init`命令，成功会显示`.git`文件

   3.向仓库中添加文件

### 4、Git远程仓库

如何将本地仓库同步到远程仓库中：

1、将远程仓库（github对应的项目）复制到本地：

```
git clone 仓库地址
```

> 注意：仓库地址在clone or download按钮下取得

2、进行文件增删改查，并添加到Git仓库中

3、将本地仓库同步到远程仓库中 使用命令：`git push`

以下本人进行本地仓库同步的完整代码 （Git为文件夹名；–Git为仓库名）

~~~
asus@DESKTOP-S0QQOSC MINGW64 ~/Desktop/技术栈/Git (master)
$ git clone https://github.com/123guo789/test.git
Cloning into 'test'...
remote: Enumerating objects: 22, done.
remote: Counting objects: 100% (22/22), done.
remote: Compressing objects: 100% (17/17), done.
remote: Total 22 (delta 4), reused 2 (delta 0), pack-reused 0
Unpacking objects: 100% (22/22), 322.69 KiB | 9.00 KiB/s, done.

~~~

~~~
asus@DESKTOP-S0QQOSC MINGW64 ~/Desktop/技术栈/Git/test (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        111.txt

nothing added to commit but untracked files present (use "git add" to track)

asus@DESKTOP-S0QQOSC MINGW64 ~/Desktop/技术栈/Git/test (master)
$ git add 111.txt

asus@DESKTOP-S0QQOSC MINGW64 ~/Desktop/技术栈/Git/test (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   111.txt


asus@DESKTOP-S0QQOSC MINGW64 ~/Desktop/技术栈/Git/test (master)
$ git commit -m '第一次远程上传'
[master 1d73314] 第一次远程上传
 1 file changed, 1 insertion(+)
 create mode 100644 111.txt

asus@DESKTOP-S0QQOSC MINGW64 ~/Desktop/技术栈/Git/test (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

asus@DESKTOP-S0QQOSC MINGW64 ~/Desktop/技术栈/Git/test (master)
$ git push
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 311 bytes | 311.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/123guo789/test.git
   63c0dae..1d73314  master -> master

~~~

### 5、搭建网站

#### 1、 个人网站

**访问**

[https://用户名.github.io](https://xn--eqr924avxo.github.io/)

**搭建步骤**

1. 创建个人站点 -> 新建仓库（注意：仓库名必须是 `用户名.github.io`）
2. 在仓库下新建`index.html`的文件

**测试**

> 注意：`github pages`只支持静态网页，仓库里面只能是`.html`文件

#### 2、项目站点

**访问**

[https://用户名.github.io/仓库名](https://xn--eqr924avxo.github.io/仓库名)

**搭建步骤**

1. 进入项目主页，点击`settings`
2. 在`settings`页面，点击`[Launch automatic page generator]`来自动生成主题页面
3. 新建站点基础信息设置
4. 选择主题
5. 生成网页