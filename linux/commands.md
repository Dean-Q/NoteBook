---
description: Linux的一些些命令
---

# Commands

## Directory Command

{% code fullWidth="false" %}
```sh
pwd: display the full path of the current location

mkdir: create a new directory
    -p: create multilevel directories
    
cd: swicth directories

ls: show the information about directory or files
    -a: display all folder information (include hiden)
    -l: display the detailed information of folder, ll for short
    -h: used in conjunction with -l, display the size of files
        (adaptive units b,k,m,g...), ls -lh for short
    -d: when follow the specified directory, can view the information about current
        directory itself
        
cp: copy file from source to target
    -r: copy directory

mv: mv [path]/file [anotherpath] for cut file
    mv fileName1 fileName2 for rename
    
touch: create a blank text file

rm: delete files or directory
    -r: recursive process
    -f: force execute
```
{% endcode %}

## File Command

```
view small file: cat head tail
    cat: suitable for viewing data within one screen
        -n: number all output lines, starts with 1
    
    head: view the first few lines of the file, default is the first 10 lines
        -n: view the first n lines
    
    tail: view the last few lines of the file, default is the last 10 lines
        -f: monitor file content updates in real time, ctrl+v to end

view large file: less
     less: the tool for paginated display the files or other output, is the linux
         orthodox view files content tools, extrmely powerful
         -m: display the precentage of the file
         -N: display the line number for each line
         /string: search down for "string"
         ?string: search up for "string"
         n: search for next one(related to / or ?)
         N: search for the next one in the oppsite direction of n
         j: scroll down a line
         k: scroll up a line
         G: jump to the end of the file
         g: jump to the file header
         q: exit
         
grep: row filter, it can use regular expressions to search for text and print out
    mathcing lines
    -i: case insensitive
    -v: reverse selection, displays the line that doesn't contain the 'search string'
        content
    main parameters of the regular expression
        \: ignore the original meaning of special characters in regular expression
        ^: match the beginning of the regular expression
        $: matchs the tail of the regular expression
        [-]: scope, such as [A-Z] will match from A to Z
        .: represent any single character, such as a..b will match a12b or aabb
        *: wildcard character
        
awk: column filter
    format: awk [-F 'separator'] '{print $n[,$n]}' filename, default separator is
    "blank key" or "tab key", which can be specified without -F, $n is used to get
    the data for the specified column
    $0: represent all columns
    $1: represent first column
    $n: represent the nth column
    example: filter all columns in text.txt with the command "awk '{print $0}' text"
    
sed: search and replace file contents
    sed -n 'Np' filename: search for data in line N of the file
    sed -n 'N1,N2p' filename: search for data in line N1 to N2 of the file
    sed -n '/sss/p' filename: search the file for the rows contain the string 'sss'
    
    sed 's/the string for search/the string for replace/g' filename: search the
        string globally for replacement, and the replaced content is output to the 
        screen(don't modify the file content)
    sed 'N1,N2 s/the string for search/the string for replace/g' filename: seach the
        string from line N1 to N2 for replacement, and the replaced content is output
        to the screen(don't modify the file content)
    sed -i 's/the string for search/the string for replace/g' filename: search the
        string globally for replacement(file content will be modified)
    sed -i 'N1,N2 s/the string for search/the string for replace/g' filename: seach 
        the string from line N1 to N2 for replacement(file content will be modified)
```





