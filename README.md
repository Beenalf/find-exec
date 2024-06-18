# find-exec
Allows users to run a pipeline of commands on all files in a specified directory

~~~ Coming Soon!  ~~~

This program was written as an assignment in the CSSE2310 class at UQ. Files in the 'include' and 'lib'
folders were provided by course staff. SVN was used for provide version control.
This is similar to the -exec functionality available with the Linux find command.

Users can specify the directory on whose files commands must be run, whether execution statistics
should be printed upon completion of the program, whether the commands on different files should be
run in parallel, and whether hidden files (those starting with ".") should be included. Recursive
functionality is not implemented, and commands are run only on regular files (not directories or
symbolic links). Wherever "{}" appears in the command pipeline, it will be replaced
by the name of the file upon which the command pipeline is currently being executed.

The command line arguments must be specified as follows:
./uqfindexec [--directory dirname] [--statistics] [--parallel] [--recurse] [--showhidden] [command]
Some example command lines are:
  ./uqfindexec
  ./uqfindexec --recurse
  ./uqfindexec "echo {} | wc -c"
  ./uqfindexec --parallel --directory /etc --showhidden --recurse 'wc -l {}'
  ./uqfindexec --showhidden "tr a-z A-Z < {} > {}.out"
  ./uqfindexec --showhidden --directory /etc 'stat {} | grep "Change: 2023" | cut -d " " -f 2'
