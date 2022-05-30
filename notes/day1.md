# Notes:

## Listing Directories
`ls`: Used to list files/folders within the current folder. Usage: `ls [options]`
Can add options:
- `-l`: Locate files and folders with more information; folders are listed with a lowercase d, whereas files are listed with dashes. Additionally, it lists permissions (string of "rwx"), the file/folder's creator, and its group (file size in octets and date)
- `-a`: Shows hidden files (i.e. in the `c-shell` directory I'm writing in, the `.git` folder will be displayed as well as `.` (current folder) and `..` (parent folder, which is `Code`)).
Options can be combined; to show both hidden files and more information, you can then write `ls -la`.

## Manual
`man`: Short for manual - allows you to get more information on another command. Synopsis displays how to use the command, while the description displays what the command does as well as options we can use. A useful feature is that you can use `man -k` to see what sort of commands you can do in each scenario (e.g. `man -k directory` displays all the commands that can be used in a directory).

## Creating and Moving within Folders
`pwd`: Shows the path of the current folder. 
`mkdir`: Creates a new folder based on the argument passed in. For example, to create the notes folder within the main directory, I could use `mkdir notes`.
`cd`: Move to the folder based on the argument passed in (or if no argument is given, moves to the personal directory `~`). For example, to go to the notes folder, I could use `cd notes`. `cd` can also be used to return to the previous folder using `cd -`.

## Creating Files
`touch`: Creates a file with the name based on the argument passed in (e.g. `touch day1.md`) created this notes file.
`cat`: View the contents of the file. Add `-e` to show line breaks (`$` will be added where there are line breaks).

## Copying/Moving Files
`cp` (Usage: `cp [file] [copyfile-name]`): copies the file `[file]` to a new file `[copyfile-name]`.
`mv` (Usage: `mv [file (path)] [new file (path)]`): moves the file `[file]` to a new file `[new file]`. Paths may be added to move it to a different folder.

## Deleting Files/Folders
`rm` (Usage: `rm [file/folder] [options]`): removes a file. Adding the `-r` option deletes all the files in a folder as well as the folder itself.
`rmdir` (Usage: `rmdir [folder]`): removes the folder `[folder]`. Folder must be empty in order to be deleted.

## UNIX rights
When using `ls -l`, each file/folder shows a string with "rwx" - this is known as the file's access permissions ('r' - read, 'w' - write, 'x' - execute). Can be separated into three sections of three characters: the first section corresponds to permissions for the file owner, the second to the owner's group, and the third to all other users.

Each permission is associated with a power of 2:
- "r": read (4)
- "w": write (2)
- "x": execute (1)
Each section is the sum of the numbers (e.g. a file that you can read/write but not execute yields the sum 6, a file with all permissions yields 7, and a file with no permissions yields 0.)

Change a file's permissions with `chmod`:
`chmod` (Usage: `chmod [num1][num2][num3] [file]`). Changes permissions for each group corresponding to the permission number. (e.g. `chmod 700 file.txt` makes the file `file.txt` only accessible to the owner.) 
