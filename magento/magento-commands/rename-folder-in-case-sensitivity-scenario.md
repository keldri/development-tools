# RENAME FOLDER IN CASE SENSITIVITY SCENARIO

## HOW TO RENAME FOLDER IN CASE SENSITIVITY SCENARIO

[https://stackoverflow.com/questions/17683458/how-do-i-commit-case-sensitive-only-filename-changes-in-git](https://stackoverflow.com/questions/17683458/how-do-i-commit-case-sensitive-only-filename-changes-in-git)

    git mv -f OldFileNameCase newfilenamecase
    
    /* Git has a configuration setting that tells it whether to be case sensitive or insensitive: core.ignorecase. To tell Git to be case-senstive, simply set this setting to false */
    
    git config core.ignorecase false