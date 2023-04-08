# Ubuntu Storage Fill up
---
tags: #self-hosted #server #ubuntu
Created ON: 2023-04-09 01:25
Relates To: [[Dev Ops Engineering]]

---
### How to find which folder is taking how much space?
* Use `df -H` to get how much free space is present.
* Now Moving to root path `/` I can run below command to check which folder is taking how  much space and do until I reach to last.
```bash
find . -maxdepth 1 -mindepth 1 -type d -exec du -sh {} \; | sort -rh | head
```
#### Explanation:

-   maxdepth says just do the find on the files in the "." directory
-   mindepth says don't include the "." directory (only look at files one level down from "."
-   the -type d flag says only match directories
-   exec says to execute the following command
-   du is the command to tell you how much disk space is used by files in a directory. the -s flag tells du to report the total from the given directory and all directories within it, not each subdirectory separately. The -h makes the bytes into human-readable format - like M for mega and G for giga.
-   exec replaces the {} symbols with the matched directory name
-   the ; simply terminates the command run by exec (the backslash escapes the ";" and the ";" ends the command)
-   then we pipe this whole output into sort which sorts the directory sizes from the find command -- the -r flag sorts in reverse order, the -h flag tells sort to interpret numbers like 10G and 10K by their value and not by their string sort order.
-   finally we pipe into head so that you don't get a screen full - you just see the top "offenders"

Some time ubuntu don't take full lvm size, it may be the case of less storage availability what we can do is following [[Increase LVM size in ubuntu]]