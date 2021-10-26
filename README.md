
# About FileA.txt
This file was blank when it got pushed but I edited it without a new commit. Using following commands after editing:
```sh
$ git add FileA.txt
$ git commit --amend --no-edit
$ git push origin --force
```
So now it looks like it has had text written into it when it was created!
# About .env
I created Item.env and pushed it, then I deleted it using these two commands:
```sh
$ git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch Item.env' --prune-empty --tag-name-filter cat -- --all
$ git push origin --force
```
So there is no record of its existence in history anymore!

# About last part
After I pushed 3 commits into ThirdBranch, I switched into the master branch (via $ git checkout master), then used following command to choose the second commit (The second commit's code is f78ae5b):
```sh
$ git cherry-pick f78ae5b
```
Then I used $ git push to add it to the master branch. <br>
At last I pulled a merge request from ThridBranch onto master branch.

