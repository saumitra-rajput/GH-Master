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

## Merge branch into main
Go to the main branch.

Now bring the changes into main:
```
git merge devops
```
Result:

Fast-forward merge

README now includes the change

## Delete the branch (cleanup)

>-d (safe delete) 

Git will delete the branch only if:

The branch is fully merged

No commits will be lost
```
git branch -d branch_name
```
>-D (force delete)

Deletes the branch no matter what =
Even if commits are NOT merged = 
Can make commits harder to find

Use this when:

Branch is experimental, 
You’re 100% sure you don’t need it, 
You want to clean up
```
git branch -D branch_name
```
## Push branches to GitHub

```
git push
```
