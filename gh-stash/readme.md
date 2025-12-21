TBU

A test Change.

## Codespace work

Make some uncommitted changes
```
code README.md
```
Check Status
```
git status
```
``You’ll see: (modified: README.md)``


Stash the changes
```
git stash
```
Output: 
Saved working directory and index state WIP on main


Check again
```
git status
```
✔️ Clean working directory
✔️ Changes are hidden, not lost


See stashed items
```
git stash list
```

Apply stash (keep stash) 

```
git stash apply
```
Restores changes
 Keeps stash in the list

Check:
```
git status
```


Apply AND remove stash (most common)

```
git stash pop
```
Restores changes/
Deletes stash entry


>Delete stashes

Delete one:
```
git stash drop stash@{0}
```


Delete all:
```
git stash clear
```

⚠️ This is permanent.