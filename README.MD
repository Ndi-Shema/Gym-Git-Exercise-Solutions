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



## Bundle 3


### Exercise 1


```

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout -b ft/team-page
Switched to a new branch 'ft/team-page'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ vi team.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git add team.html
warning: in the working copy of 'team.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git commit -m "new team page"
[ft/team-page bf2f5fa] new team page
 1 file changed, 21 insertions(+)
 create mode 100644 team.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git push origin ft/team-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 525 bytes | 262.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions/pull/new/ft/team-page
remote:
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/team-page -> ft/team-page

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout -b ft/contact-page
Switched to a new branch 'ft/contact-page'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/contact-page)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git log
commit bf2f5fa13c1e8b5a588fa3b103ab4d6238dc4191 (HEAD -> ft/team-page, origin/ft/team-page)
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Fri May 19 01:28:19 2023 +0200

    new team page

commit 2660016b68c65c28894867b6f0519de7183376f5 (origin/main, main, ft/contact-page)
Author: Ndi-Shema <106658796+Ndi-Shema@users.noreply.github.com>
Date:   Fri May 19 00:53:01 2023 +0200

    Update README.MD

commit d1577a05e7a352ec2509d14d2ba266200b58ab74
Merge: f1dbe8f 1f96867
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Fri May 19 00:45:16 2023 +0200

    Merging main branch into ft/service-redesign

commit f1dbe8fd1756b1ddc62da9b868a55031763c3c31
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Fri May 19 00:20:11 2023 +0200

    additional changes to service.html in main

commit 1f96867002a29f5247d539fa4d038054b90051fc
Merge: 5e64354 ea7c71e
Author: Ndi-Shema <106658796+Ndi-Shema@users.noreply.github.com>
Date:   Fri May 19 00:16:25 2023 +0200

    Merge pull request #4 from Ndi-Shema/ft/service-redesign

    Redesigned the service.html page

commit ea7c71eeae6ebc27535eaae7f98ad27a8b56b75c
Author: Ndi-Shema <f.shema@alustudent.com>
Date:   Fri May 19 00:10:35 2023 +0200

    Redesigned the service.html page

commit 5e64354df9e30c4aaa3641b603d995b6f84fab1b
Author: Ndi-Shema <106658796+Ndi-Shema@users.noreply.github.com>
Date:   Fri May 19 00:04:45 2023 +0200

    Update README.MD

commit 000f364a6967d23bf4d2e9da15294b775a7de014
Merge: c59592c f6113ad
Author: Ndi-Shema <106658796+Ndi-Shema@users.noreply.github.com>
Date:   Thu May 18 23:54:56 2023 +0200

    Merge pull request #3 from Ndi-Shema/ft/bundle-2

    service page added

commit f6113ade91b48ba8c57dffd8b88ece1ba5619758 (origin/ft/bundle-2, ft/bundle-2)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git checkout ft/contact-page
Switched to branch 'ft/contact-page'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/contact-page)
$ git cherry-pick bf2f5fa13c1e8b5a588fa3b103ab4d6238dc4191
[ft/contact-page bd3535e] new team page
 Date: Fri May 19 01:28:19 2023 +0200
 1 file changed, 21 insertions(+)
 create mode 100644 team.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/contact-page)
$ git add .

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/contact-page)
$ git commit -m "contact page"
On branch ft/contact-page
nothing to commit, working tree clean

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/contact-page)
$ git push origin ft/contact-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 530 bytes | 265.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:
remote:      https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions/pull/new/ft/contact-page
remote:
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/contact-page -> ft/contact-page

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/contact-page)
$ git checkout -b ft/faq-page
Switched to a new branch 'ft/faq-page'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/faq-page)
$ vi faq.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/faq-page)
$ git add faq.html
warning: in the working copy of 'faq.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/faq-page)
$ git commit -m "adding a faq.html page"
[ft/faq-page 03bc44d] adding a faq.html page
 1 file changed, 22 insertions(+)
 create mode 100644 faq.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/faq-page)
$ git push origin ft/faq-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 443 bytes | 443.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions/pull/new/ft/faq-page
remote:
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/faq-page -> ft/faq-page

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/faq-page)
$ git checkout ft/team-page
Switched to branch 'ft/team-page'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git revert bf2f5fa13c1e8b5a588fa3b103ab4d6238dc4191
[ft/team-page 4dbb94b] Revert "new team page"
 1 file changed, 21 deletions(-)
 delete mode 100644 team.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git push origin ft/team-page
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 281 bytes | 281.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
   bf2f5fa..4dbb94b  ft/team-page -> ft/team-page

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$
```

### Exercise 2

``` 

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout ft/faq-page
Switched to branch 'ft/faq-page'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/faq-page)
$ git checkout -b ft/home-page-redesign ft/faq-page
Switched to a new branch 'ft/home-page-redesign'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/home-page-redesign)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ ls
README.MD  bundle-1  faq.html  service.html  team.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ vi home.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git add .
warning: in the working copy of 'home.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git commit -m "updating the home page"
[main 6c7d9cd] updating the home page
 1 file changed, 46 insertions(+)
 create mode 100644 home.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 711 bytes | 711.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
   c549195..6c7d9cd  main -> main

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout ft/home-page-redesign
Switched to branch 'ft/home-page-redesign'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/home-page-redesign)
$ git rebase main
Successfully rebased and updated refs/heads/ft/home-page-redesign.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/home-page-redesign)
$ git add .

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/home-page-redesign)
$ git commit -m "Rebasing home page"
On branch ft/home-page-redesign
nothing to commit, working tree clean

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/home-page-redesign)
$ git push origin ft/home-page-redesign
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions/pull/new/ft/home-page-redesign
remote:
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/home-page-redesign)
$
```


## Bundle 4

### Exercise 1

```

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/team-page)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git remote add git-copy https://github.com/Ndi-Shema/Git-exercise-clone-repo.git

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ ls
README.MD  bundle-1  faq.html  home.html  service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ vi home.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git add .

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git commit -m "updating the home page"
[main 6c00ea4] updating the home page
 1 file changed, 1 insertion(+), 1 deletion(-)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 312 bytes | 312.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
   bffa6b4..6c00ea4  main -> main

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git push git-copy main
Enumerating objects: 71, done.
Counting objects: 100% (71/71), done.
Delta compression using up to 8 threads
Compressing objects: 100% (69/69), done.
Writing objects: 100% (71/71), 17.90 KiB | 4.47 MiB/s, done.
Total 71 (delta 27), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (27/27), done.
To https://github.com/Ndi-Shema/Git-exercise-clone-repo.git
 * [new branch]      main -> main

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$
```


### Exercise 2

```
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout -b ft/footer
Switched to a new branch 'ft/footer'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ ls
README.MD  bundle-1  faq.html  home.html  service.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ vi footer.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ git add footer.html
warning: in the working copy of 'footer.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ git commit -m "footer page"
[ft/footer 900cd62] footer page
 1 file changed, 4 insertions(+)
 create mode 100644 footer.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ vi footer.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ git add .
warning: in the working copy of 'footer.html', LF will be replaced by CRLF the next time Git touches it

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ git commit -m "more changes in the footer page"
[ft/footer 631bd00] more changes in the footer page
 1 file changed, 1 insertion(+)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ git push origin ft/footer
Enumerating objects: 19, done.
Counting objects: 100% (19/19), done.
Delta compression using up to 8 threads
Compressing objects: 100% (14/14), done.
Writing objects: 100% (14/14), 2.64 KiB | 2.64 MiB/s, done.
Total 14 (delta 7), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (7/7), completed with 3 local objects.
remote:
remote: Create a pull request for 'ft/footer' on GitHub by visiting:
remote:      https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions/pull/new/ft/footer
remote:
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/footer -> ft/footer

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/footer)
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git checkout -b ft/squashing
Switched to a new branch 'ft/squashing'

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/squashing)
$ git merge --squash ft/footer
Updating 6c00ea4..631bd00
Fast-forward
Squash commit -- not updating HEAD
 footer.html | 5 +++++
 1 file changed, 5 insertions(+)
 create mode 100644 footer.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/squashing)
$ git commit -m "footer changes squashing"
[ft/squashing 043d726] footer changes squashing
 1 file changed, 5 insertions(+)
 create mode 100644 footer.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/squashing)
$ git push origin ft/squashing
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 355 bytes | 355.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/squashing' on GitHub by visiting:
remote:      https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions/pull/new/ft/squashing
remote:
To https://github.com/Ndi-Shema/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/squashing -> ft/squashing

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (ft/squashing)
$
```


## Bundle 5

### Exercise 1

```
Github page: https://ndi-shema.github.io/Gym-Git-Exercise-Solutions/
```


### Exercise 2

```
Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ git clone https://github.com/Ndi-Shema/git-cafe-exercise.git
Cloning into 'git-cafe-exercise'...
remote: Enumerating objects: 107, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 107 (delta 5), reused 4 (delta 4), pack-reused 100
Receiving objects: 100% (107/107), 1.95 MiB | 2.44 MiB/s, done.
Resolving deltas: 100% (5/5), done.

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises (main)
$ cd git-cafe-exercise/

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises/git-cafe-exercise (main)
$ la
bash: la: command not found

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises/git-cafe-exercise (main)
$ ls
README.md  css/     index-1.html  index-3.html  index.html
bat/       images/  index-2.html  index-4.html  js/

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises/git-cafe-exercise (main)
$ vi index.html

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises/git-cafe-exercise (main)
$ git add .

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises/git-cafe-exercise (main)
$ git commit -m "welcome message changed to Restaurant"
[main f9a06fb] welcome message changed to Restaurant
 1 file changed, 2 insertions(+), 2 deletions(-)

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises/git-cafe-exercise (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 340 bytes | 340.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Ndi-Shema/git-cafe-exercise.git
   d1d3f9c..f9a06fb  main -> main

Lenovo@DESKTOP-CF2VEAG MINGW64 ~/Bundle_exercises/git-cafe-exercise (main)
$
```
