# Lab Report 5
## Find Command
The Find command works as follows:

`find Directory`

This will display all the files under a specified folder (in this case, Directory). This will include folders, and files under those folders.

Typing `find .` or just `find` without specifying the directory will display all files under the current directory.

## find -type
Syntax: `find Directory -type d`, `find Directory -type f`

This will display all files under Directory that are of a specific type. Using `-type d` finds directories under the file, while `-type f` finds all the files.

### Example 1
```console
find . -type f
```
Produces the following results:

```console
./Abernathy/ch1.txt
./Abernathy/ch14.txt
./Abernathy/ch15.txt
./Abernathy/ch2.txt
./Abernathy/ch3.txt
./Abernathy/ch6.txt
./Abernathy/ch7.txt
./Abernathy/ch8.txt
./Abernathy/ch9.txt
./Berk/CH4.txt
./Berk/ch1.txt
./Berk/ch2.txt
./Berk/ch7.txt
...
```
As you can see, all the files are .txt and there are no directories.

### Example 2
```console
find . -type d
```

Produces the following results:
```console
.
./Abernathy
./Berk
./Castro
./Fletcher
./Kauffman
./Rybczynski
```
Now all of these are directories. Note that the current directory is also listed.

## find -name
Syntax: `find Directory -name "filename"`

This will display all the files under Directory with the name filename. This flag is case-sensitive. To do a search that is not case-sensitive, `find Directory -iname "filename"` should be used.

### Example 1
```console
find . -name "ch1.txt"
```

Produces the following results:
```console
./Abernathy/ch1.txt
./Berk/ch1.txt
./Fletcher/ch1.txt
./Kauffman/ch1.txt
./Rybczynski/ch1.txt
```

All the files named ch1.txt are listed.

### Example 2
```console
find . -name "ch*"
```

Produces the following results:
```console
./Abernathy/ch1.txt
./Abernathy/ch14.txt
./Abernathy/ch15.txt
./Abernathy/ch2.txt
./Abernathy/ch3.txt
./Abernathy/ch6.txt
./Abernathy/ch7.txt
./Abernathy/ch8.txt
./Abernathy/ch9.txt
./Berk/ch1.txt
./Berk/ch2.txt
./Berk/ch7.txt
...
```
Using the asterix, we find all the files whose names starts with ch. This allows you to specify which type of file you want to find (for example, doing `*.png` finds all png image files).

## find -size
Syntax: `find Directory -size +SIZE`, `find Directory -size SIZE`, `find Directory -size -SIZE`
Finds all files under Directory whose size is greater than, equal to, or less than SIZE, respectively for `+SIZE`, `SIZE`, and `-SIZE`.

Size is measured in bytes:
* b = 512 bytes
* w = two-byte words
* c = byte
* k = kilobyte
* M = megabyte
* G = gigabyte

### Example 1
```console
find . -size +100k
```

Produces the following results:
```console
./Berk/CH4.txt
./Berk/ch2.txt
```

Using the -size flag, we are able to identify the biggest files in our directory by specifying files above 100 kilobytes.

### Example 2
```console
find . -size -20k
```

Produces the following results:
```console
.
./Abernathy
./Berk
./Castro
./Castro/chN.txt
./Castro/chO.txt
./Castro/chQ.txt
./Castro/chW.txt
./Castro/chY.txt
./Castro/chZ.txt
./Fletcher
./Kauffman
./Rybczynski
```

By specifying our files to be less than 20 kilobytes, we found the smallest files and directories.

## find -mtime
Syntax: `find Directory -mtime +TIME`, `find Directory -mtime TIME`, `find Directory -mtime -TIME`

This will display all files under Directory which were created greater than, equal to, or less than TIME days ago, respectively for `+TIME`, `TIME`, and `-TIME`.

### Example 1
```console
find -mtime -20
```

Produces the following results:
```console
.
./Abernathy
./Abernathy/ch1.txt
./Abernathy/ch14.txt
./Abernathy/ch15.txt
./Abernathy/ch2.txt
./Abernathy/ch3.txt
./Abernathy/ch6.txt
./Abernathy/ch7.txt
./Abernathy/ch8.txt
./Abernathy/ch9.txt
./Berk
...
```

Since all the files were cloned less than 20 days ago, the entire directory is listed.

### Example 2
```console
find -mtime +1
```

Produces the following results:
```console

```

There are no results because there are no files created more than 1 day ago.

## Works Cited
* https://www.youtube.com/watch?v=dQw4w9WgXcQ (jk)
* https://www.youtube.com/watch?v=KCVaNb_zOuw
* https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size
