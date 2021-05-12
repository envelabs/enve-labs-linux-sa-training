# fudamentals
list of generic unix/linux commands for system administration

### conventions
1. text between `< >` represents values that should be completed
2. text between `[ ]` represents optional values


### commands
`passwd` command: change current user passwd

    passwd


change <user> passwd

    passwd <user>


`whoami` command: returns effective uid

    whoami
    <user-id>

`whoami` through `sudo`

    sudo whoami
    [sudo] password for <user-id>:
    root

`id` command: returns user identity information

    id
    <user-id> <group-ide>...

returns user info for specific user

    id <user-name>
    <user-id> <group-ide>...

### manual Pages
`man` command: manual pages for specific command

    man <command>


manual pages that refers to <keyword>

    man -k <keyword>


### moving around
`pwd` command: where are we or the present work directory?

    pwd


`ls` command: listing files

    ls


`cd` command: change directory

    cd <path>


`mkdir` command: make directory

    mkdir <dir1> [dir2]


`rm` command: remove directory

    rm -fr <dir1>


make multiple directories at the same time

    mkdir -p <dir1>/{<subdir1>,<subdir2>,<subdir3>}


### finding files:<br>
the `which` command searches through the directories that are defined in the `$PATH` environment variable for a given file name. This variable contains a listing of directories that the system searches when a command is issued without its path. If a match is found, which returns the full path to the file as shown below:

`$PATH` environment variable:<br>

    echo $PATH
    /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin


`which` command:<br>

    which ls
    /bin/ls


`locate` command:<br>
find location of files or dir previously stored in the update.db database loaded by `updatedb` command. The database is automatically updated on a regular basis by the cron scheduler

    updatedb
    locate *locate.db
    /var/lib/mlocate/mlocate.db


`find` command:<br>
find file or directory based in name or other param(s)

    sudo find /etc/ -name passwd
    /etc/passwd
    /etc/pam.d/passwd
