
Path Handling means working with files and folder paths ,
creating them, joining them , checking if they exist , etc

Python’s `os` and `os.path` modules help you handle such paths in a **cross-platform** way (i.e., your code works on both Linux and Windows).

You can do bulk actions  in terms of making folders , renaming files and more.

To Know the full path of file and  use it `programmatically` , you often have pieces of the location:

So to join that path we use:
`os.path.join()`

```
import os

folder="Downloads"
filename="hey.txt"

path = os.path.join("home/user",folder,filename)
print(path)
```

Alternatively,
we can use, `pathlib`

```
from pathlib import Path

path = Path("home/user")/"Downloads"/"hey,txt"
```

Output(in Linux):
```
/home/user/Downloads/hey.txt
```


If you want a filename from a full path , for that we use , `os.path.basename()`

```
import os

path ="home/user/YOs/blue.txt"
print(os.path.basename(path))

#returns blue.txt
```

and if you only want directories, not file name , you gotta use , `os.path.dirname()`
```
import os 

path = "/home/user/Documents/hey.txt"
print(os.path.dirname(path))

#returns /home/user/Document
```

and if you want to split filename and directories from your path you gotta use,
`os.path.split()`

```
import os 

path= "/home/user/Document/notes.txr"
print(os.path.split(path))

#returns  ('/home/user/Documents', 'notes.txt')
```

If you want to check if a path exists or not, use, `os.path.exists()`

```
import os

if os.path.exists("/home/user/Documents"):
print("Path exists!")
```

TO check if a path is a file or directory: `os.path.isfile()`  and `os.path.isdir()`

```
print(os.path.isfile("/home/user/Documents/notes.txt"))  # True or False
print(os.path.isdir("/home/user/Documents"))             # True or False

```

IF You want the absolute path (path from the root).
you gotta use, `os.path.abspath`

```
print(os.path.abspath("notes.txt"))
```

If you want to clean your path by removing redundant separators , you gotta use,
`os.path.normpath()`

```
print(os.path.normpath("/home/user/../user/Documents//notes.txt"))
# Output: /home/user/Documents/notes.txt

```

Creating and Navigating Directories

```
os.mkdir("new_folder")          # Create a single directory
os.makedirs("a/b/c")            # Create nested directories
os.chdir("a/b/c")               # Change current working directory
print(os.getcwd())              # Get current working directory

```

Path Handling in Action

```
import os

# Current directory
current_dir = os.getcwd()
print("Current Directory:", current_dir)

# Join path
file_path = os.path.join(current_dir, "data", "info.txt")
print("File Path:", file_path)

# Check existence
if not os.path.exists(os.path.dirname(file_path)):
    os.makedirs(os.path.dirname(file_path))  # Create if not exists

# Create a file
with open(file_path, "w") as f:
    f.write("Path handling example")

print("File Created at:", file_path)

```

## Alternative: `pathlib` (Modern Way)
`pathlib` is object-oriented and generally preferred over `os.path` for new projects.

Python’s newer library for path handling:

```
from pathlib import Path

p = Path("/home/user/Documents/notes.txt")
print(p.name)       # notes.txt
print(p.parent)     # /home/user/Documents
print(p.exists())   # True/False
print(p.suffix)     # .txt

```
