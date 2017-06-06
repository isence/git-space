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
git log --graph --pretty=oneline --abbrev-commit
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

##分支
Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>
=====
合并某分支到当前分支：git merge <name>

合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。
git merge --no-ff -m "merge with no-ff" <name>
=====
删除分支：git branch -d <name>

当Git无法自动合并分支时，就必须首先解决冲突。解决冲突后，再提交，合并完成。

用git log --graph命令可以看到分支合并图。


修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除；

当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场。
