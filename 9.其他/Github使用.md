```
git config --global user.name "Author Name"
git config --global user.email "Author Email"
```

修改最近一次提交的作者

```
git commit --amend --author="NewAuthor <NewEmail@address.com>"
```

删除某次commit

```
git log // 查询要回滚的 commit_id
git reset --hard commit_id // HEAD 就会指向此次的提交记录 hard此次提交之后的修改不做任何保留
git reset --soft commit_id // 此次提交之后的修改会被退回到暂存区,不会被删除
git push origin HEAD --force // 强制推送到远端
```

本地分支与远程分支冲突

```
git pull --rebase origin master
```



### …or create a new repository on the command line



```
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/KeyForce/test.git
git push -u origin main
```

### …or push an existing repository from the command line



```
git remote add origin https://github.com/KeyForce/test.git
git branch -M main
git push -u origin main
```



提交现存的仓库到目标仓库

```
git init
git config user.name "name"
git config user.email "email"
git remote add origin <链接>
git pull origin master
  
git branch
git add .
git commit -m "First commit"
git push origin master
```

