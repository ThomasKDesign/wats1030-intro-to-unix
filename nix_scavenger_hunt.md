# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:
   */home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* * Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?
   *LICENSE    challenge_files        nix_scavenger_hunt_stretch.md  
    README.md  nix_scavenger_hunt.md
  
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?
  *The files are much more detailed in ls -alh. The file sizes, dates of creation?, are included with the  ls -alh command. The size of the files are in rounded up to 2 digits too.
  
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/)Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
    * -ls -a : Include directory entries whose names begin
             with a dot (.).
    -ls -l : List in
             long format. If the output
             is to a terminal, a total sum for all the
             file sizes is output on a line before the
             long listing.   
    -ls -h : When used with the -l option, use unit suf-
             fixes: Byte, Kilobyte, Megabyte, Gigabyte,
             Terabyte and Petabyte in order to reduce
             the number of digits to three or less using
             base 2 for memorys/file sizes.

         
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?* 
  *Files/Directories listed in my root   - bin   dev  fastboot  lib    media  opt   root  sbin  sys  usr     
  boot  etc  home      lib64  mnt    proc  run   srv   tmp  var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:
   */home/cabox  

   
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:* 
  */home/cabox  

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
  *2015_special_stuff.demo	cloaked-wookie.demo scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
  *Entering 'cd' takes me up back to one directory up, 'workspace'.

* Press the up arrow on your keyboard. *What just happened?*
  *The last commands appeared.

* Press the up arrow a few more times. *What do you see?*
  *Every single time, the commands appear in order of usage.

* Run the `history` command. *What do you see?*
  *History command lists all the commands I ran.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
  *Supposedly my usename, in CodeAnywhere it's cabox, and my local terminal it's 'thomaskaiaua'.

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
  *'who' command reveals it's just me 'cabox', and interestingly, it lists 2 caboxs, as I have 2 SSH terminals open!

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
  *11:55:29 up  1:29,  2 users,  load average: 0.00, 0.00, 0.00   

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
  *It lists the accessed directories and processes, with the type of CPU memory used, duration, and by user or what machine the user accessed them from.
  
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
  *It lists the processes in real time, updating the content as they change.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
 *2 files, ./credit_cards.txt, ./credit_cards2.txt.                                                                          

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
  *1995? I'm guessing here, as I exhausted my search for usage of 'more' command.

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
  *./tmp/modi_laboriosam.txt
  
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
  *2 files, Britt-Erdman.user:O'Harachester, WA 37261                                                    
   Lissie-Strosin.user:Jewessfurt, WA 00816-7241 

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
  *serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis si
   t explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse
   blanditiis dolorem culpa non quia. 
  

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
  *It lists the files that have texts in them. 
  
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
  *the list is are shown one file per line, which is much clearer to read.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
  *This command summarized the processes list in just 2 lines below;
  cabox     1620  0.0  0.1   8816   768 pts/2    S+   13:33   0:00 grep --color=auto thomaskaia
   ua 
