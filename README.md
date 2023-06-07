# path-helper

path_helper is a Python utility script designed to facilitate the handling of file and directory paths across different operating systems. It provides a consistent way to input and process paths, whether you're on Windows, macOS, or Linux.

## Requirements
- Python 3.6 or higher
- pathlib library (included with Python 3.4+)

## Usage

path_helper provides two functions:
- get_path(): Prompts the user to enter a folder path. It interprets input paths correctly across different operating systems, including interpreting ~ as the home directory on Unix/Linux systems. The function returns a pathlib.Path object.
- convert_path(path): Takes a pathlib.Path object or a string, and returns the path as a string with backslashes converted to forward slashes for compatibility.

You can use these functions in your scripts like this:

```python
from path_helper import get_path, convert_path

# Prompt the user to enter a folder path
path = get_path()

# Convert the path to a string with forward slashes
path_str = convert_path(path)
```

This way, you can easily use path_helper to handle paths in your own projects.
## Example

Let's say you're on Windows, and you run a script that uses path_helper:

```
Enter folder path: C:\Users\Username\Documents
```

The get_path() function will return a pathlib.Path object representing the entered path. If you pass this object to convert_path(), it will return:

```
C:/Users/Username/Documents
```

Or, if you're on a Unix/Linux system and you enter:

```bash
Enter folder path: ~/Documents
```

The get_path() function will return a pathlib.Path object representing the absolute path to your Documents directory. convert_path() will then return this path as a string.