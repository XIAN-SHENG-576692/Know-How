# First Step to Developing a Repository

```bash
git init
```

```bash
git remote add origin <REPO>
```

```bash
git pull origin <BRANCH> --tags
```

# Push to remote

```bash
git add .
```

```bash
git commit
```

```bash
git push -u origin <BRANCH>
```

# Rename a branch

```bash
git branch -m <BRANCH_A> <BRANCH_B>
```

```bash
git push -u origin <BRANCH_B>
git push origin --delete <BRANCH_A>
```

References
- [How to rename the "master" branch to "main" in Git | Learn Version Control with Git](https://www.git-tower.com/learn/git/faq/git-rename-master-to-main)

# Cancel the latest commit

```bash
git reset HEAD^
```

References
- [菜鳥工程師 肉豬: Git 取消未push的commit](https://matthung0807.blogspot.com/2021/07/git-cancel-last-unpushed-local-commit.html)

# Common

```bash
git log
```

```bash
git log --oneline
```

```bash
git log --graph --oneline --decorate
```

```bash
git log --graph --oneline --decorate --all
```
References
- [[2025-10-10]] 15:25
- GitHub branch 視覺化.mhtml
- [How To Visualizing Branch Topology in Git? - GeeksforGeeks](https://www.geeksforgeeks.org/git/how-to-visualizing-branch-topology-in-git/?utm_source=chatgpt.com)


---

```bash
git status
```

---

```bash
git branch
```

```bash
git checkout <branch>
```

---

```bash
git tag -l
```

```bash
git tag -a <NEW_TAG>
```

---

[Git 進階應用 Submodule 與 Subtree，使用它們來拆分專案 | Puck's Blog](https://blog.puckwang.com/posts/2020/git-submodule-vs-subtree/)

[[2025-10-21]] 11:58

```bash
git submodule add <repo url> <folder>
```

```bash
git submodule update --recursive
```

```bash
git submodule deinit -f <submodule folder>
rm -rf .git/modules/path/to/submodule
git rm -f path/to/submodule
```

```bash
git clone <repo url> --recurse-submodules
```

```bash
git submodule init
git submodule update

# or

git submodule update --init
```

```bash
git clone <Super Repo>
git remote rm origin
git filter-branch --subdirectory-filter <SubModule folder path> -- --all
git remote add origin <SubModule Repo>
git push
git rm -r <folder>
git submodule add <git repository B url> <folder>
git commit
git push
```
