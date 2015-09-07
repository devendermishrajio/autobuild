# Repo Sync Script

##Dependencies
It requires following tools:
- git
- repo
- dch
- dpgk-buildpackage

## What does it do?
It makes package for trusty package.

It does the following:
 - It get the repositories.
 - For each repository, it generates head of the repo into manifest file.
 - For each project, it compares if there is any change, then it does packaging.
      - It calls git log between old head and current head.
      - If old and current head are different, then it writes the log information into git log file.
      - Else, it writes the existing head info to git log file.

After that, for each line, it calls dch command. 
