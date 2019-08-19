# c203: Week 04 

In addition to Programming 3.1 in the Notebook this week: 

We have 3 tiny small programs (and an accompanied `Makefile`)
to play with pointers, linked lists and `gdb`/`valgrind`.
You'd better to follow the instructions in the bottom to transfer the 
whole directory to your Jupyter workplace first. Then run 
```bash
make
```
and try.
The programs include:
* [`list_abc.c`](/.list_abc.c): a very, very simple program that
created 3 separate data nodes and then join them together into
a list. Then, it will insert one node in the midle of the list.
The program works, but it probably has some errors. If you try:
```bash
make
gdb ./list_abc
```
You probably see that the program is correct. Now try:
```bash
valgrind ./list_abc
```
You'll see that the program has some memory leaks. Do what `valgrind`
told you to do and then try to find the errors and fix it.


* [`llist.c`](./llist.c) is a more serious program to work with lists.
It creates a list of 10 integers, and then deletes some of them.
Here, the function `delete_kth` employs a *pointer to pointer* variable,
which helps to keeps the function short, but which makes the function
a bit difficult to understand. Try to understand it. Keep in mind
that after `pa= &a;`, `*pa` and `a` both refer to *the same object* in
 the memory. 
Also note that `llist.c` has errors. It's worth to try with `gdb` first
this time.    


* **HOWTO:** Use `random_friend.c` which contains a number of runtime errors 
to practice with `gdb` and `valgrind`. 

* Start `gdb` by using Jupyter's Terminal to run
```bash
make
gdb -tui ./afriend
```
Then, inside `gdb` first try the following sub-commands
```bash
r
where
b 20
r
s
s
```
You might realize that it take too long to run the program step by
step. You can avoid it by
first shorten the loops in `random_friend.c` by changing line 20 from
```c
	int n= 50;
```
to
```c
	int n= 2;
```
and the rerun `make` and `gdb`.   

* Start valgrind with
```bash
valgrind ./afriend
```
`valgrind` will output a report. You should analyse the report to
figure out the problem with the code.   

* Learn this [`Makefile`](./Makefile) and build a similar one
for the `Programming 3.1` of the lab.  

-------------------------------------------------------------------
## HOW_TO: download/copy the files from this github repository

If you just want a single file, say, **Makefile**:
  * Click on the link **Makefile** (at the top of this github) and you will see its content 
  * Copy the content and paste into your editor's window before saving on a driver. The easiest way to copy is (a) click on `Raw` to see the plain text content, then (b) press Ctrl-A then Ctrl-C to copy the whole content.  

If you want to download the whole directory:
  * Download this whole directory by clicking `Clone or Download` --> `Download ZIP`, it will normally be downloaded to your *Downloads* directory under the name **c203** or **c203.ZIP** (it might also have a suffix **-master**)
  * Then copy or move the directory **c203** from **Downloads** to under your working directory **week2/**
  * If the downloaded **c203** has the extension **.ZIP**, you likely need to expand the zipped file with command **unzip c203.ZIP**

### How to transfer a file or the whole directory from this github site into your JupyterLab working directory?

You can just use `git clone`. Run the following command in a Jupyter's Terminal window:
```bash
git clone http://github.com/anhvir/c203
```
And you will see a new folder `c203` under your current directory.

-------------------------------------------------------------
by avo@unimelb.edu.au, for use in unimelb COMP20003 workshops.

For a teaching week, a new content is (normally) uploaded at the very beginning of the week, and that content is removed one week later.
