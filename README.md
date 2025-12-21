## Branching.
What is a Git branch? 

A branch is an independent line of work

>main = stable code

Other branches = experiments / features / learning

You can switch, merge, or delete branches safely


>Branch = parallel universe

To Create branch.
```
git branch branch_name
```
To list the branches
```
git branch
```
To delete the use flag -D followed by branch_name
```
git branch -D branch_name
```
To rename the branch if target exists use flag -M
```
git branch -M branch_name
```
Switch to the new branch
```
git checkout branch_name
or 
git switch branch_name (Morden way)
```

Make changes in the new branch
```
code README.md
```
## Branching Practice
This change is in learn-branching branch.

Commit the change (only in this branch)
```
git add README.md
git commit -m "Add branching practice notes"
```
>This commit exists only in learn-branching.


### Yes, it worked
The change is gone

Because main doesn’t have that commit









## This Readfile is updated and merged while cloning
 gh-clone-HTTPs.
## Sub folder with the Clone repo via HTTPS. 

So This repo is again created inside the Existing GH repo.

Our motive is to clone a GH repo in local folder in Codespace

Make changes in the readme.md file

Save the file and push the Folder to origin(Main remote GH repo)

## Steps
create a folder in main GH repo
```
mkdir gh-clone-HTTPs
```
```
cd gh-clone-HTTPs
```
Make changes into the existing readme.md file.
```
code readme.md
```
Go back to the main repo
```
cd ..
```
Add the git changes.

```
git add gh-clone-HTTPs
```
Commit the changes.
```
git commit -m "your message"
```
Push to the GH repo.
```
git push
```
## TA daaa Not working yet
This will be all you need to do.
You have successfuly clone the Existing GH repo.

Make changes and Push to the GH repo.


## Error 

Why your README changes don’t appear on GitHub

Because:

The outer repo (GH-basics) only knows:

“This submodule points to commit X”

It does not know or care about file changes inside the submodule

GitHub will never show those inner file changes unless:

You commit them inside the inner repo

And push them to that repo’s remote

## You WANT a submodule (advanced, intentional)

If this folder should stay a separate repo:

## Fix
Commit & push inside submodule

```
cd gh-clone-HTTPs/GH-basics
git add README.md
git commit -m "Update README in submodule"
git push
```
Update pointer in parent repo

```
cd ../../
git add gh-clone-HTTPs/GH-basics
git commit -m "Update submodule pointer"
git push
```