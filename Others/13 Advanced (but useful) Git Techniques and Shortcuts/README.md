# [13 Advanced (but useful) Git Techniques and Shortcuts - YouTube](https://www.youtube.com/watch?v=ecK3EnyGD8o)

[[2022-04-10]] 12:13

01:06

```bash
git add .
```

```bash
git commit -m <message>
```

```bash
git commit -am <message>
```

01:44

```bash
git config --global alias.ac <command>
```
- for example:
    ```bash
    git config --global alias.ac "commit -am"
    ```

    ```bash
    git ac <message>
    ```

01:52

```bash
git commit --amend -m <new message>
```

```bash
git commit --amend --no-edit
```

02:14

CAUTION: overwrite the remote commit with the state of your local code.
```bash
git push origin master --force
```

02:31

```bash
git revert <commit>
```

02:59

On your GitHub repo web
press `Shift + .` will open online VS Code editor

`TERMINAL -> Continue Working on... -> Create New Codespace` set up a full power VS Code.

Other references
- [GitHub Codespaces · GitHub](https://github.com/features/codespaces)

03:22

```bash
git stash
```

```bash
git stash save <stash name>
```

```bash
git stash list
```

```bash
git stash apply 0
```

04:14

Post 2020, "master" is no longer the preferred nomenclature.

04:25

```bash
git branch -m <new branch name>
```

04:42

```bash
git log --graph --oneline --decorate
```

05:01

Use binary search to walk you through each commit.
```bash
git bisect start
```

External Reference
- [使用 Git Bisect 快速找到第一個有問題的 Commit：叡揚部落格 (gss.com.tw)](https://www.gss.com.tw/blog/%E4%BD%BF%E7%94%A8-git-bisect-%E5%BF%AB%E9%80%9F%E6%89%BE%E5%88%B0%E7%AC%AC%E4%B8%80%E5%80%8B%E6%9C%89%E5%95%8F%E9%A1%8C%E7%9A%84-commit)

05:28

How to squash the commits.

```bash
git rebase
```

```bash
git commit --fixup <commit>
```

```bash
git commit --squash <commit>
```

```bash
git rebase -i --autosquash
```

External Reference
- [git - How can I easily fixup a past commit? - Stack Overflow](https://stackoverflow.com/questions/3103589/how-can-i-easily-fixup-a-past-commit)
- [[Git] Rebase - 使用 Interactive 模式來精簡 commit 紀錄 | 搞搞就懂 - 點部落](https://dotblogs.com.tw/wasichris/2016/05/04/re)
- [[Git] Reset - mixed, hard and soft | 搞搞就懂 - 點部落](https://dotblogs.com.tw/wasichris/2016/04/29/225157)

06:31

`.git/hooks`

If you are a javascript developer, you can use [Husky](https://typicode.github.io/husky/) that makes it much easier to configure git hooks

07:09

Go back to your remote version.
CAUTION: your local repo would be permanently deleted.
```bash
git fetch origin
```

```bash
git reset --hard origin/main
```

clean the untracked files
```bash
git clean -df
```

completely clean the `.git` folder
```bash
rm -rf .git
```

07:49

Go to previous branch
```bash
git checkout -
```
