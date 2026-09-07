#linux 

```bash
ls -i # for getting inode/index number of a file
echo $MAIL # getting path of user's mail
```

- /etc/password: stores usernames, UIDs, GIDs and home directories
- /etc/shadow: stores user passwords

## The find command

```bash

find / -type f -name *.conf -user root -size +20k -newermt 2020-03-03 -exec ls -al {} \; 2>/dev/null
```

|**Option**|**Description**|
|---|---|
|`-type f`|Hereby, we define the type of the searched object. In this case, '`f`' stands for '`file`'.|
|`-name *.conf`|With '`-name`', we indicate the name of the file we are looking for. The asterisk (`*`) stands for 'all' files with the '`.conf`' extension.|
|`-user root`|This option filters all files whose owner is the root user.|
|`-size +20k`|We can then filter all the located files and specify that we only want to see the files that are larger than 20 KiB.|
|`-newermt 2020-03-03`|With this option, we set the date. Only files newer than the specified date will be presented.|
|`-exec ls -al {} \;`|This option executes the specified command, using the curly brackets as placeholders for each result. The backslash escapes the next character from being interpreted by the shell because otherwise, the semicolon would terminate the command and not reach the redirection.|
|`2>/dev/null`|This is a `STDERR` redirection to the '`null device`', which we will come back to in the next section. This redirection ensures that no errors are displayed in the terminal. This redirection must `not` be an option of the 'find' command.|


## File Descriptors

A file descriptor (`FD`) in Unix/Linux operating systems is a reference, maintained by the kernel, that allows the system to manage Input/Output (`I/O`) operations. It acts as a unique identifier for an open file, socket, or any other I/O resource

By default, the first three file descriptors in Linux are:

1. Data Stream for Input
    - `STDIN – 0`
2. Data Stream for Output
    - `STDOUT – 1`
3. Data Stream for Output that relates to an error occurring.
    - `STDERR – 2`

- STDIN is the input we provide
- STDOUT is the output of any command
- STDERR is the error produced by any command
#### Redirect STDIN

As we have already seen, in combination with the file descriptors, we can redirect errors and output with greater-than character (`>`). This also works with the lower-than sign (`<`). However, the lower-than sign serves as standard input (`FD 0 - STDIN`). These characters can be seen as "`direction`" in the form of an arrow that tells us "`from where`" and "`where to`" the data should be redirected. We use the `cat` command to use the contents of the file "`stdout.txt`" as `STDIN`.

````shell-session
cat < stdout.txt
````

#### Redirect STDOUT to a File

Now we can see that all errors (`STDERR`) previously presented with "`Permission denied`" are no longer displayed. The only result we see now is the standard output (`STDOUT`), which we can also redirect to a file with the name `results.txt` that will only contain standard output without the standard errors.

````shell-session
find /etc/ -name shadow 2>/dev/null > results.txt
````
#### Redirect STDERR to a file

We can redirect the file descriptor for the errors (`FD 2 - STDERR`) to "`/dev/null`." This way, we redirect the resulting errors to the "null device," which discards all data.

````shell-session
find /etc/ -name shadow 2>/dev/null
````

> Use '>>' to append contents and '>' to write content in a file

#### Redirect STDIN Stream to a File

We can also use the double lower-than characters (`<<`) to add our standard input through a stream. We can use the so-called `End-Of-File` (`EOF`) function of a Linux system file, which defines the input's end. In the next example, we will use the `cat` command to read our streaming input through the stream and direct it to a file called "`stream.txt`."

````shell-session
cat << EOF > stream.txt
````

> This is so cool. Don't know what use it is though

