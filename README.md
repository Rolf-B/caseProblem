# caseProblem
Showcase the git case problem for windows NTFS Folder 

Steps to create the problem:

- use Windows 10 with WSL (Windows Subsystem for Linux) enabled
- create a folder as parent folder for your local repo clone. For example: D:\Git_CS
- use `fsutil file setcasesensitiveinfo D:\Git_CS enable` to make filenames in this folder case sensitive. This won't work without WSL!
- clone this repo into this folder. Windows adopts the case sensitive state for new folders, so the repo folder and all of its subfolders will have the casesensitive state too.
- You can check this with `fsutil file querycasesensitiveinfo D:\Git_CS\caseProblem`
- Run `git status` for the cloned repository. Foo.txt should be reported as modified, just after you cloned the repo.
