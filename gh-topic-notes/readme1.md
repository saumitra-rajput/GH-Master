## A readme.md file inside GH repo
Because 

Two README.md files in the same directory

Not possible (same name, same path)

## Key Concept (must remember)

One GitHub repo = one .git directory

You now have two independent repos:

GH-basics/.git ← main repo (already linked to GitHub)

GH-basics/gh-00/.git ← new, separate repo (this is the problem)


## Mistakes
I was trying to create new readme.md file inside repo.

I created a folder>added read.md file

Then I initiated the folder command ```git init``` to make it git repo so it can have ```.git``` file in hidden directories.

## Fix
cd into the new folder

check the .git file ```ls -la``` to show hidden folders.

delete .git
 ```
 rm -rf .git
 ```

```cd .. ``` go back to the main repo

add the folder ```git add folder_name```

```
git commit -m "your message "
```

```
git push
``` 
## Ta Da 

Your folder readme.md file will be added in your GH repo.

Which was created in Codespace.