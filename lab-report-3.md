# Lab Report 3

## Four Command Line Arguments for Find

### -name

**Example 1**

```
find . -name WhatToGreek.txt
```

**Output:**

```
./written_2/travel_guides/berlitz1/WhatToGreek.txt
```

The command -name searches the directory after "find" to look for a file by its name and returns the path.
This is useful because you may know the what the file was called but can't remember which directory the file was saved in.

**Example 2**

```
find . -name ch1.txt
```

**Output:**

```
./written_2/non-fiction/OUP/Berk/ch1.txt
./written_2/non-fiction/OUP/Abernathy/ch1.txt
./written_2/non-fiction/OUP/Rybczynski/ch1.txt
./written_2/non-fiction/OUP/Kauffman/ch1.txt
./written_2/non-fiction/OUP/Fletcher/ch1.txt
```

If you use find -name it will list all of the files with that name. But if I were to change it to a specific directory like "." to "written_2/non-fiction/OUP/Fletcher -name ch1.txt the output would only be "written_2/non-fiction/OUP/Fletcher/ch1.txt"

### -size

**Example 1**

```
find written_2/non-fiction/OUP/Kauffman -size -1M
```

**Output:**

```
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Kauffman/ch3.txt
written_2/non-fiction/OUP/Kauffman/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch4.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch7.txt
written_2/non-fiction/OUP/Kauffman/ch6.txt
written_2/non-fiction/OUP/Kauffman/ch8.txt
written_2/non-fiction/OUP/Kauffman/ch9.txt
written_2/non-fiction/OUP/Kauffman/ch10.txt
```

The -size command returns all the files that fit the amount of megabytes searched for. Before putting the size amount you can either use - or + to determine if you want less then that amount of megabytes or higher. In the example above I looked for files below 1 MB and it returned all the files within Kauffman.

**Example 2**

```
find written_2 -size +1M
```

**Output:**
```
nothing
```

Compared to the previous example, the only change was the directory and instead of "-" it was "+". Nothing was returned because none of the files in all of written_2 exceeded 1 MB.

### -type d

**Example 1**

```
find written_2 -type d
```

**Output:**

```
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Castro
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```

In this example command -type d lists all the directories within written_2 and the directories within those as well.


**Example 2**

```
find written_2/non-fiction -type d
```

**Output:**

```
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Castro
```

In this example I made the path more specific so the command -type d only listed the directories within non-fiction so this time it didn't include the one from travel guides like in example 1.

### -type f

**Example 1**

```
find written_2/non-fiction/OUP/Abernathy -type f
```

**Output**

```
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
```

The command -type f only returns files within that directory and does not list directories in the output.

**Example 2**

```
find written_2/non-fiction/OUP/Fletcher -type f
```

**Output**

```
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Fletcher/ch6.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/non-fiction/OUP/Fletcher/ch10.txt
```

In this example it only returned the files from Fletcher but if I made the path writen_2/non-fiction/OUP it would've returned all the files from Abernathy, Berk, Castro, Fletcher, Kauffman, and Rybczynski.

### Sources Used
https://www.tecmint.com/35-practical-examples-of-linux-find-command/
