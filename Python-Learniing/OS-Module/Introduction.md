The OS module in Python is a part of the standard library and provides a way to interact with the operating system.It allows you to work with files, directories, environment variables and processes - all in a platform-independent way(works on Windows , Linux , mac .etc )


- Use `os`  for low-level OS interactions and legacy APIs.
- Prefer `pathlib` for modern path handling(object-oriented)
- Use `shutil` for copying/removing whole directory trees and high-level file ops.
- Use `subprocess` for spawning external processes instead of `os.system`/  `os.spawn` in most cases

## Importing OS module

```
import os
```

