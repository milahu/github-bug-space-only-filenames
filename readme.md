# github-bug-space-only-filenames

when there are files with space-only filenames, then the github blob api says

> Sorry, we had to truncate this directory to 1,000 files. 2 entries were omitted from the list.

## ls

```
$ ls
' '  '  '   license.txt   readme.md

$ ls "  "
somefile.txt
```

## build

```sh
#!/usr/bin/env bash

cd $(mktemp -d)
git init
echo test >" "
git add " "
mkdir "  "
echo test >"  "/somefile.txt
git add "  "
git commit -m init

# git remote add github https://github.com/milahu/github-bug-space-only-filenames
# git push github
```
