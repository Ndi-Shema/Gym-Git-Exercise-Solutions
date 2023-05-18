# GIT Exercises

## Bundle 1

### Exercise 1

```

Lenovo@DESKTOP-CF2VEAG MINGW64 ~ (main)
$ cd Bundle_exercises/

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git init
Initialized empty Git repository in C:/Users/Lenovo/Bundle_exercises/.git/

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (master)
$ git branch -m main

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ touch bundle-1

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git add -all
error: did you mean `--all` (with two dashes)?

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git add --all

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git commit -m "Bundle exercises"
[main (root-commit) 7548311] Bundle exercises
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 bundle-1

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git remote add https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
usage: git remote add [<options>] <name> <url>

    -f, --fetch           fetch the remote branches
    --tags                import all tags and associated objects when fetching
                          or do not fetch any tag at all (--no-tags)
    -t, --track <branch>  branch(es) to track
    -m, --master <branch>
                          master branch
    --mirror[=(push|fetch)]
                          set up remote as a mirror to push to or fetch from


Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git remote add origin https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 221 bytes | 221.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout -b dev
Switched to a new branch 'dev'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git checkout -b test
Switched to a new branch 'test'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (test)
$ git branch dev
fatal: a branch named 'dev' already exists

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (test)
$ git checkout dev
Switched to branch 'dev'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git branch -d test
Deleted branch test (was 7548311).

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$
```



### Exercise 2


```

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ touch home.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ vi home.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash save "Exercise 2: Stashing"
Saved working directory and index state On dev: Exercise 2: Stashing

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ vi about.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash save "Exercise 2 about: Stashing"
No local changes to save

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git add .
warning: in the working copy of 'about.html', LF will be replaced by CRLF the next time Git touches it
warning: in the working copy of 'home.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash save "Exercise 2 about: Stashing"
Saved working directory and index state On dev: Exercise 2 about: Stashing

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ vi team.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git add .
warning: in the working copy of 'team.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash save "Exercise 2 team: Stashing"
Saved working directory and index state On dev: Exercise 2 team: Stashing

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash list
stash@{0}: On dev: Exercise 2 team: Stashing
stash@{1}: On dev: Exercise 2 about: Stashing
stash@{2}: On dev: Exercise 2: Stashing

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html

Dropped stash@{1} (2786c2cdbf4afb56a3da41f5a4bf79d8b874a836)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash pop stash@{2}
fatal: log for 'stash' only has 2 entries

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash list
stash@{0}: On dev: Exercise 2 team: Stashing
stash@{1}: On dev: Exercise 2: Stashing

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html
        new file:   home.html

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    README.MD

Dropped stash@{1} (0624ee5646a27975c9e0a746ed07020c09908f22)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git add .

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git commit -m "home and about pages"
[dev 25ff5d8] home and about pages
 3 files changed, 44 insertions(+), 84 deletions(-)
 delete mode 100644 README.MD
 create mode 100644 about.html
 create mode 100644 home.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git push origin dev
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 8 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (7/7), 1.89 KiB | 1.89 MiB/s, done.
Total 7 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions/pull/new/dev
remote:
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      dev -> dev

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash pop stash@{1}
fatal: log for 'stash' only has 1 entries

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash list
stash@{0}: On dev: Exercise 2 team: Stashing

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git stash pop stash@{0}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped stash@{0} (2a20a9fb7ae82b0e4da944347aca00d87e53025b)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$ git reset --hard HEAD
HEAD is now at 25ff5d8 home and about pages

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (dev)
$

```



## Bundle 2

### Exercise 1


```

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/bundle-2)
$ touch service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/bundle-2)
$ git add .

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/bundle-2)
$ git commit -m "service page added"
[ft/bundle-2 f6113ad] service page added
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/bundle-2)
$ git push origin ft/bundle-2
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 288 bytes | 288.00 KiB/s, done.
Total 2 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
   91467a3..f6113ad  ft/bundle-2 -> ft/bundle-2

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/bundle-2)
$

```




