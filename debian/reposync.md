# Repo Sync Script
This script:
- Generates build log from the repository (using comments from commit) from the updated repository
- Generates the package source.

##Dependencies
It requires following tools:
- git: A popular SCM tool which is based on distributed version control.
- repo
- dch or debchange: It adds new comment line into the Debian changelog.
- dpgk-buildpackage: It builds binary or source package from source.

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

