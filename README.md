# caseProblem
Showcase the git case problem for windows NTFS Folder 

Steps to create the problem:

- use Windows 10 with WSL (Windows Subsystem for Linux) enabled
- make sure that you didn't enable git option `core.ignorecase` on a global level
- create a folder as parent folder for your local repo clone. In this text, I will use the folder `D:\Git_CS`.
- use `fsutil file setcasesensitiveinfo D:\Git_CS enable` to make filenames in this folder case sensitive. This won't work without WSL!
- clone this repo into `D:\Git-CS`. Use `caseProblem` as local name. Windows adopts the case sensitive state for new folders, so the repo folder and all of its subfolders will have the casesensitive state too.
- open a shell and navigate to `D:\Git_CS\caseProblem`
- check with `fsutil file querycasesensitiveinfo D:\Git_CS\caseProblem` that the folder is indeed case sensitive (try `type foo.txt` and `type Foo.txt` too).
- check with `git config core.ignorecase` that this flag has not been set by the clone process (which would happen when you clone into a case insensitive folder)
- Run `git status` for the cloned repository. Foo.txt should be reported as modified, just after you cloned the repo.
- 
