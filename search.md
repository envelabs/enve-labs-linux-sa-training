# Search Commands
there are different utilities that can be used to find files in a linux system

#### locate
in order to use this command we need to update the database
```
$ updatedb
$ locate bash
/bin/bash
/bin/rbash
/etc/bash.bashrc
/etc/bash_completion
```

#### which
the `which` command searches for commands through the directories defined in the `$PATH` environment variable
```
$ which bash
/bin/bash
```

#### find
the `find` command is a powerful tool that can be use in order to locate files based in different criterias like name, creation time, ownership, etc
```
$ find / -name "bash"
/bin/bash
/usr/share/doc/bash
```
