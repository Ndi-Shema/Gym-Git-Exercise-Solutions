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


### Exercise 2

```

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/bundle-2)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git pull origin main
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), 1.40 KiB | 62.00 KiB/s, done.
From https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions
 * branch            main       -> FETCH_HEAD
   c59592c..5e64354  main       -> origin/main
Updating c59592c..5e64354
Fast-forward
 README.MD    | 21 ++++++++-------------
 service.html |  0
 2 files changed, 8 insertions(+), 13 deletions(-)
 create mode 100644 service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ $ git checkout -b ft/service-redesign
bash: $: command not found

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout -b ft/service-redesign
Switched to a new branch 'ft/service-redesign'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ ls
README.MD  bundle-1  service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ vi service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git add service.html
warning: in the working copy of 'service.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git commit -m "Redesigned the service.html page"
[ft/service-redesign ea7c71e] Redesigned the service.html page
 1 file changed, 41 insertions(+)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git push origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 792 bytes | 792.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions/pull/new/ft/service-redesign
remote:
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/service-redesign -> ft/service-redesign

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ vi service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git add service.html
warning: in the working copy of 'service.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ vi service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git add service.html
warning: in the working copy of 'service.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git commit -m "additional changes to service.html in main"
[main f1dbe8f] additional changes to service.html in main
 1 file changed, 40 insertions(+)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git push origin main
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git diff main
diff --git a/service.html b/service.html
index 2edd987..1015ea6 100644
--- a/service.html
+++ b/service.html
@@ -20,7 +20,7 @@

   <section>
     <h2>Service 1</h2>
-    <p> Management Services.</p>
+    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum efficitur quam vitae varius malesuada. Ut a ullamcorper mauris, id cursus nisi.</p>
   </section>

   <section>
@@ -38,3 +38,4 @@
   </footer>
 </body>
 </html>
+

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git merge main
Auto-merging service.html
CONFLICT (content): Merge conflict in service.html
Automatic merge failed; fix conflicts and then commit the result.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign|MERGING)
$ git commit -m "merge main branch into ft/service"
error: Committing is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
U       service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign|MERGING)
$ vi service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign|MERGING)
$ git add service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign|MERGING)
$ git commit -m "merge main branch into ft/service"
[ft/service-redesign b211d40] merge main branch into ft/service

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git push origin ft/service-redesign
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 ! [rejected]        ft/service-redesign -> ft/service-redesign (fetch first)
error: failed to push some refs to 'https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git diff main
diff --git a/service.html b/service.html
index 2edd987..066efde 100644
--- a/service.html
+++ b/service.html
@@ -20,7 +20,11 @@

   <section>
     <h2>Service 1</h2>
+<<<<<<< HEAD
+    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum efficitur quam vitae varius malesuada. Ut a ullamcorper mauris, id cursus nisi.</p>
+=======
     <p> Management Services.</p>
+>>>>>>> main
   </section>

   <section>
@@ -38,3 +42,7 @@
   </footer>
 </body>
 </html>
+<<<<<<< HEAD
+
+=======
+>>>>>>> main

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git pull origin main
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 642 bytes | 160.00 KiB/s, done.
From https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions
 * branch            main       -> FETCH_HEAD
   5e64354..1f96867  main       -> origin/main
Merge made by the 'ort' strategy.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git push origin ft/service-redesign
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 ! [rejected]        ft/service-redesign -> ft/service-redesign (fetch first)
error: failed to push some refs to 'https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git checkout main
Switched to branch 'main'
Your branch and 'origin/main' have diverged,
and have 1 and 2 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git pull origin main
From https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions
 * branch            main       -> FETCH_HEAD
Auto-merging service.html
CONFLICT (content): Merge conflict in service.html
Automatic merge failed; fix conflicts and then commit the result.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main|MERGING)
$ git checkout ft/service-redesign
error: you need to resolve your current index first
service.html: needs merge

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main|MERGING)
$ git merge main
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main|MERGING)
$ vi service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main|MERGING)
$ git add service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main|MERGING)
$ git commit -m "Merging main branch into ft/service-redesign"
[main d1577a0] Merging main branch into ft/service-redesign

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git push origin ft/service-redesign
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 ! [rejected]        ft/service-redesign -> ft/service-redesign (fetch first)
error: failed to push some refs to 'https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout ft/service-redesign
Switched to branch 'ft/service-redesign'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git pull origin ft/service-redesign
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 633 bytes | 20.00 KiB/s, done.
From https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions
 * branch            ft/service-redesign -> FETCH_HEAD
   ea7c71e..56d0061  ft/service-redesign -> origin/ft/service-redesign
Merge made by the 'ort' strategy.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git push origin ft/service-redesign
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (8/8), 1.06 KiB | 1.06 MiB/s, done.
Total 8 (delta 5), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (5/5), completed with 2 local objects.
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
   56d0061..7dd59e8  ft/service-redesign -> ft/service-redesign

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/service-redesign)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git push origin main
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 364 bytes | 364.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
   1f96867..d1577a0  main -> main

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$
```




