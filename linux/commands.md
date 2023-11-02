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
        
|: pipe character
    command1 | command2: the output of command1 is taken as the input of command2
    note: pipe character handles only the correct output of the previous command
        and not handle the incorrect output
        
find: search for file or directory
    note: the directory uses find command can not be a link
```

## Output and Input redirection

```
>: standard output overwrites wirte file
>>: standard output appends to file

cat: connect file or standard input and print, this command is usually used to
    display the content of file
    cat << EOF: end with EOF input character as standard input
    cat > filename: create new file and put standard input and output into the
        filename file, end with 'ctrl+d'
```

## Remote network Command

```
scp: copy data from local host to remote server
    format: scp [-r] file_To_Copy remote_UserName@remote_Host_Ip:targetLocation
    
ssh: login remote server from localhost
    format: ssh userName@Host_Ip
    ssh-copy-id userNmae@Host_Ip: register the local public key certificate file with
        the remote server, and then we can login using the private key certificate
```

## Process Command

```
ps: the abbreviation of Process status, this command will list a snapshot of the
    current processes that were running at the time the ps command was executed
    -aux: view all processes on the system,using BS operating system format
        (with CPU and memory information)
        Decription of the command execution result:
            USER:owner of process PID:id of process PPID:parent process id
            %CPU:cpu percentage used by a process  %MEM: percentage of memory usgae
            VSZ:the amount of virtual memory used by the process(KB)
            RSS:the process uses physical memory
            TTY:if it is "pts/0", means the host process is connected to the network
            stat:process status
            Z:zombie process   <:high priority process  N:low priority process
            L:some page locked into memory
            s:the leader of process(with child processes below it)
            START:start time when process is triggered
            TIME:the actual cpu usage time of the process
            COMMAND: name and parameter of command
    -ef: view all processes on the system, using Liunx standard command format
        (with PID)
            Description of the command execution result:
                UID: id of user,but actual is user name
                PID: id of process PPID:praent process id
                C:percentage of cpu used by process
                STIME:start time of process
                TTY:which terminal is the process running on, if the process is
                independent of the terminal, the system will display "?". if the
                value is pts/0, it indicates that the host proess is connected by
                the network
                TIME:the time of cpu already be occupied by the process
                CMD: name and parameter of command
                
    ps often used with grep to find specific process, like ps -aux | grep sshd
    
kill: terminate process
     kill pid: wait for execution to finish and then terminate process(not mandatory)
     kill -9 pid: force to terminate process
     
     
top: real-time monitor process, will display the information about the processed
    running in the current system, includes pid, memory usage and cpu usage

    
```
