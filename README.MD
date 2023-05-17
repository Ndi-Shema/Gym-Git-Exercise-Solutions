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
