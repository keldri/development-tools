# Git Commands

- See all Remote Branches

        git branch -a

---

- Checkout a tracking branch from remote branch

    *remote branch can be found by using above command.

        git branch -t <remote branch>
        
        // example will checkout to a new fresh upstream/develop branch
        git checkout -t remotes/upstream/develop

---

- See Release Tag

    *Helpful when trying to determine what accelerator or bryant park release a project is on

        git describe --tags

---

- Git diffs between 2 commits

        `git diff ID1 ID2`

---

- Revert commits

        `git revert <commit>`

---

- See original committer

        `git blame <file>`

---

- Undo last commit

        `git reset --hard HEAD~1`

---

- Undo last published commit

        `git revert HEAD~1..HEADgit revert <commitid>`
        

---

- Undo git add

        `git reset filename`

---

- Git Config

    Add user Name

        git config --global user.name "Kate Eldridge"

    Add user email

        git config --global user.email "keldridge@somethingdigital.com"

    Style colors

        git config --global color.ui auto
        git config --global color.branch auto
        git config --global color.status auto