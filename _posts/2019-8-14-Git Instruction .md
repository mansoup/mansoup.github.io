

------

## **1. What is git? What is difference  between git and SVN**

### Git 是分布式版本控制系统,而SVN是集中式版本控制系统。

>**集中式版本控制系统** ：版本库集中放在中央服务器，用户若要提交修改内容，必须要从中央服务器下载最新版本，方可提交修改，这就要求很高的网速。
>
>**分布式版本控制系** ： 没有中央服务器，每个人都有版本库，无需联网，若要多人协作只需把自己修改的push上去，其它用户客户可以pull下来更新，相对而言对网速要求变低。

### Git working principle

![git working principle](\images\git working principle.png)

## **2.Install Git**

> 从网上下载git安装包一直默认安装下去，在任意界面下点击右键都会有git GUI here 和 git bash here 。

<img src="/images/git-bash.png" width="20%">

>安装过程需要配置用户名和邮箱用来标识是谁提交的
>
>`git config --global user.name **"yourname"**`
>
>`git config --global user.email **"youremail"**`

## 3.Git Command

> * **git init**  : 例如在github目录下面使用该命令则会产生一个隐藏文件`.git`。
>
> * **git add 文件名** : 会将文件添加到暂存区内，提交到暂存区前使用`git status` 命令，修改的文件颜色会是红色的，一旦添加到暂存区则显示绿色。
>
> * **git commit -m "your explain"** : 将文件提交到本地仓库。
>
> * **git log** :查看commit暂存区提交到本地库的提交次数、版本号、提交解释和时间内容等。
>
>   ![git log](\images\git-log.png)
>
> * **git reset --hard HEAD^3** : 既然上图有这么多版本，我想要回到某个具体版本可以用上面命令，这个数字**3**表示向前退三版本，这个数字可以为大于**0**的整数。
>
> * **git diff 文件名** ：查看文件提交至本地仓库之后在工作区到底修改了什么。
>
> * **git reflog** :在使用回滚之后可以查看回滚之前版本指针，还有显示更简洁。
>
> * **git reset --hard 版本地址** ：跳转特定版本

## **2. Exemple**

> 1. 现在重新创建的LIENCE，内容是This is a big project! 查看状态。
>
>     ![未提交到暂存区](\images\README-1.png)
>
> 2. 提交了之后
>
>    ![提交到暂存区之后](\images\README-2.png)
>
> 3. 此时将README提交到本地仓库之前，改变README内容添加`my Blog`
>
>    ![提交仓库前修改README](\images\README-3.png)
>
> 4. 查看提交本地仓库之后，修改工作区文件内容，前后对比
>
>    ![对比](\images\README-4.png)
>
> 5. 查看commit之后个版本信息，HEAD代表目前指向此版本
>
>    ![查看版本](\images\README-5.png)
>
> 6. 回滚一个版本查看版本信息，注意回滚主要对commit即本地仓库的回滚
>
>    ![回滚](\images\README-6.png)
>
> 7. 现在想把回滚取消了，回到 update 2
>
>    ![跳转特定版本](\images\README-7.png)
>
> 8. 

## **4. What is differenct between workspace and repository?**

> **工作区** ：主要是你在电脑`git bash here` 界面文件目录，但是不包括隐藏文件`.git`文件夹。
>
> **本地库**： 即`.git` 文件夹，版本库里面存了很多东西，其中最重要的就是stage(暂存区)，还有Git为我们自动创建了第一个分支master,以及指向master的一个指针HEAD。

## **5. Git revoke the amendment and delete file operation**

> **在工作区修改内容后但是没有提交至暂存区，该怎么放弃这次修改呢？**
>
> 1. 我们可以直接打开文件修改内容。
>
> 2. 可以使用版本回滚（我不明白，不是没有提交至本地仓库，怎么回滚？）
>
> 3. 使用 `git checkout -- 文件名`命令来恢复工作区原来内容。
>
>    * 一种是未提交到暂存区的修改，该命令会撤销还原与版本库一致内容
>
>    * 另一种是已经提交到暂存区后，再在暂存区修改，如果此时用checkout则是还原至暂存区内容。
>
>      ![工作区添加内容](\images\README-8.png)
>
>      ![暂存区添加后checkout](\images\README-9.png)
>
> **删除本地仓库的文件**
>
> * 直接使用` rm 文件名`,回复使用`git checkout -- 文件名` 注意空格！

## **6. Push and clone from remote**

> 推送本地库内容到远程库前要先设置远程库地址使用`git remote origin 地址`，查看提交地址使用`git remote -v`。
>
> ![push to remote](\images\README-10.png)
>
> 从远程仓库克隆：`git clone 仓库地址`。
>
> ![clone](\images\README-11.png)

## **7. Creat and merge branch**

> 创建分支，分支切换。
>
> ![分支问题](\images\README-12.png)
>
> 合并分支，删除分支。
>
> ![分支问题](\images\README-13.png)

## **8. Branch conflict**

> **分支冲突** ： 在分支Branch1 添加了内容后提交至本地仓库，在主分支master同样对同一文件修改，此时使用`git merge Branch1`会产生冲突错误，此时可以`git log` 回退或者将主分支与分支修改内容统一即可。
>
> **分支管理** ：一般情况下`git merge Branch1`之后Branch1会消失，要想这个分支不消失可以采用`git merge --no-ff -"注释" Branch1`的方式使得Branch1不会消失，一般情况下master分支是用来提交的发布新版本，而其他分支是用来工作的，其它分支修改完之后可以采用merge方式合并至主分支，最后提交。