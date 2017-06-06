##提交代码
git status //查看状态
git diff //查看变化
git add . //准备提交
git commit -m "change"//提交
git status

##版本回退

HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

git log //查看日志
//回退之前版本
git reset --hard HEAD^
git reset --hard HEAD^^
git reset --hard HEAD^^^
git reset --hard HEAD~100

git reflog //查看记录下的每一次命令
git reset --hard 3628164//指定版本

##工作区和缓冲区
git checkout -- readme.txt//撤销工作区
git reset HEAD readme.txt//撤销缓冲区

##删除文件
git rm test.txt //本地删了，想删除版本库某个文件
git checkout -- test.txt//本地误删了，想从版本库恢复某个文件

##远程仓库
要关联一个远程库，使用命令 git remote add origin git@github.com:isence/git-space.git

关联后，使用命令git push -u origin master第一次推送master分支的所有内容；

此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；
