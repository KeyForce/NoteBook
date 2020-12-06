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
