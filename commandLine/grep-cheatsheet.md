# Grep

## **Flags List**

    -i: case-insensitive search
    -w: whole word search
    -r: recursive search
    -v: inverted search
    -L or --files-without-match
    -l or or --files-with-match
    -A: provide context lines after search-term
    -B: provide context lines before search-term
    -V: provide context lines before/after search-term
    -H: print filename for each match
    -n: print the line number before each line that matches.

## Reg Ex

    \A: single character
    
    [abc]: Range. ie any one of these characters
    
    [^abc]: Not range. A character that is not one of those enclosed.
    
    (abc): Group these characters and remember for later.
    \n: Replace n with a number. Recall the charactes matched in that set of brackets.May also be used to rename files or directories.
    
    |: The logical 'or' operation.
    
    \: In front of a character, removes it's special meaning.

## RE Multipliers

    ?: The preceding item is optional, it is matched zero or one times.
    
    *: The preceding item will be matched zero or more times.
    
    +: The preceding item will be matched one or more times.
    
    {n}: The preceding item will be matched exactly n times.
    
    {n,}: The preceding item will be matched n or more times.
    
    {n,m}: The preceding item will be matched between n and m times.
    

## RE Anchors

    ^: From the beginning of the line.
    
    $: To the end of the line.
    
    \<: At the beginning of a word.
    
    \>: At the end of a word.
    
    \b: Match either the beginning or end of a word.

**Case-insensitive Search**

    ## <grep> <case-insensitive search> <search-term> <file>
    grep -i 'asdf' testfile

---

**Whole Word Search**

    ## <grep> <whole word search> <search-term> <file>
    grep -w 'test' testfile

---

**Recursively Search - search for term in all subfolders of directory**

    ## <grep> <recursive search> <search-term> <path to directory>
    grep -r '456' root/testfile:filename

---

**Inverted Search - search out all lines in file except word**

    ## <grep> <inverted search> <search-term> <path to directory>
    grep -v 'practicle' testfile

---

**Provide Context Search —After - search out all lines in file except word**

    ## <grep> <provide context><num of lines after to add> <search-term> ##<path to directory>
    grep -A3 'practical' testfile

---

**Provide Context Search —Before  - search out all lines in file except word**

    ## <grep> <provide context><num of lines before to add> <search-term> ##<path to directory>
    grep -B3 'practical' testfile

---

**Provide Context Search —Before/After  - search out all lines in file except word**

    ## <grep> <provide context><num of lines before/after to add> <search-term> ##<path to directory>
    grep -C3 'practical' testfile

---

[Examples](https://www.notion.so/97fd53cab4ee4158a224231215f9567f)