<h1>Linux Basics</h1>

<code>echo Hi</code>
will print to screen

<code>ls</code>
will list files and folders in current location

<code>cd</code>
will change the directory by using cd followed by the file or folder

<code>pwd</code>
will print the currently directory you are in

<code>mkdir</code>
will make a new folder / directory

<code>cd new_directory; mkdir new_folder; pwd</code>
you can run multiple commands by using the semicolon followed by the next command in order. In this example it will enter into the new_directory, create a new folder and then present the current workign directory 

<code>mkdir -p /tmp/asia/india/bangalore</code>
by using the -p command we can create a directory tree in one command input instead of creating each directory or folder individually

<code>rm -r /tmp/my_dir1</code>
this will remove the directory called my_dir1

<code>cp -r my_dir1 /tmp/my_dir1</code>
will copy the directory called my_dir1

<code>touch new_file.txt</code>
will create a new text file called new_file in the current directory

<code>cat > new_file.txt</code> add text to the file then control + d to exit

<code>cat new_file.txt</code> to view the contents of the file

<code>cp new_file.txt copy_file.txt</code> this will copy the file

<code>mv new_file.txt sample_file.txt</code> this will move file, if its in the same location it will work as if its renamed

<code>rm new_file.txt</code> to remove a file

<h1>VI editor Linux</h1>

<code>vi index.html</code>
opens the editor in command mode  
-type i to enter insert mode  
-press esc to go back to command mode  
-move around using the arrow keys or 'k' for up 'h' for left 'j' for down 'l' for right  
-to delete a character press 'x' or 'dd' to delete the whole line  
-to copy a line type 'yy' and to paste it type 'p'  
-type :w to save the command  
-type :w example to save the a file called filename  
-type :q to quit / discard changes
-type :wq to save the file and quit  
-type /of to find text 'of' followed by 'n' to find the next occurance of that specific text
-type 



