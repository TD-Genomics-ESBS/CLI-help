# Command Line Cheat Sheet

## Help commands

### Display the manual of a command

### Display the help a command

In function of command, it's `-h` or/and `--help` option.

```bash
<command> -h
<command> --help
```

```bash
man <command>
```

By example:

man ls # display the manual of the ls command
```

## File system navigation

### Display path of current directory

It's allow you to know where you are in the file system.

```bash	
pwd 
```

### Change directory to <directory>

```bash
cd <directory>
```

### Navigate to parent directory

```bash 
cd ..
```

You can use several `..` to go to the parent directory of the parent directory, etc. By example, if you are in the directory `/home/user/td/results` and you want to go to the directory `/home/user`, you can use:

```bash 
cd ../..
```

### List directory contents

Without any option, It's allow you to know what is in the current directory. You can add the `-l` option to display more information about the files and directories.The `-a` option will display hidden files and directories (theses file names begins with a `.`). You can also combine options.

You can add the path of a specific directory to list the content of this directory.

```bash   
ls # display the content of the current directory
ls -la # display the content of the current directory with more information and display also the hidden files and directories
ls /home/user # display the content of the directory /home/user
```

### Write path

It's important to know the difference between relative and absolute path. 

**Absolute path**: the path from the root directory to the file/directory. It's always start with `/`.

```bash
/absolute/path/to/file
```

**Relative path**: the path from the current directory to the file/directory. It's never start with `/`.

```bash
relative/path/to/file
```

By example, if you are in the directory `/home/user` and you want to go to the file `/home/user/data/file`, you can use the absolute path or the relative path:

```bash
cd /home/user/data/file # absolute path
cd data/file # relative path
```

If you are in the directory `/home/user/td` and you want to go to the file `/data/`, you can use the absolute path or the relative path:

```bash
cd /data # absolute path
cd ../../data # relative path
```

```bash
## File and directory manipulation

### Create new directory named <directory>

```bash 
mkdir <directory>
```

### Remove a <file> or a <directory> 

```bash
mkdir <file>
mkdir -r <directory>
```

### Copy <file> / <directory> (and it's contents) to a new <destination> (possibly overwriting an existing file/directory)

```bash
cp <file> <destination>
cp -r <directory> <destination>
```

The destination can be the directory where you want copy the file/directory or the new name of the file/directory.

### Move <file> / <directory> (and it's contents) to a new <destination> (possibly overwriting an existing file/directory)

```bash
mv <file> <destination>
mv <directory> <destination>
```

Destination: see `cp` command.

### Delete <file> or <directory>

```bash
rm <file>
rm -r <directory>
```

### Create an empty file named <file>

```bash
touch <file>
```

## File content manipulation

### Display the all content of <file>

```bash
cat <file>
```

### Display content of <file> in interactive mode

```bash
more <file>
```

Q: to quit
RETURN: to see the next file
ESPACE: to nee the next page

### Display the first lines of <file>

By default, display the 10 first lines. Add the `-n` option to display the first *n* lines.

```bash
head <file> 
head -n 12 <file> # display the first 12 lines
```

### Display  the last lines of <file>

By default, display the 10 last lines. Add the `-n` option to display the last *n* lines.

```bash	
tail <file>
tail -n 5 <file> # display the last 5 lines
```

### Display a zip file content

```bash
zcat <file>
```

### Count the number of lines in <file>

```bash
wc -l <file>
```

## Output manipulation

### Redirect the output of a command to a new file

Use `>` to redirect the output of a command to a new file. If the file already exists, it will be overwritten.

```bash
<command> > <file>
```

### Append the output of a command to a file

Use `>>` to append the output of a command to a file. If the file doesn't exist, it will be created. If the file exists, the output will be appended to the end of the file.

```bash
<command> >> <file>
```

### Redirect the output of a command to the input of another command

The pipe `|` is used to redirect the output of a command to the input of another command.

```bash
<command1> | <command2>
```

By example, to count the number of lines of a zipped file:

```bash
zcat <file> | wc -l
```

## Network

### Etablish an SSH connection to <host> with <user>

```bash
ssh <user>@<host>
```

By example, for LBGI servers:

```bash
ssh <login>@tp.lbgi.fr
```

Copy file from a remote host to the local host (your computer)

```bash
scp <user>@<host>:/remote/path /local/path
```

*Important:* The `/remote/path` has to be an absolute path.


By example, to copy a file from the LBGI server to your computer:

```bash
scp <login>@tp.lbgi.fr:/data/TDdenovo/readsSJ1L04_1.fq.gz .
```

## Other commands

### Launch python

```bash
python3
```

### Run fastqc

```bash
fastqc -o <output_directory> <reads> 
```

