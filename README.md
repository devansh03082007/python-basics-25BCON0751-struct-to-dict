# python-basics-25BCON0751-struct-to-dict
this is a python program to convert structured data into dictionaries 
# struct_to_dict

A small Python helper that converts a ctypes `Structure` into a dictionary.

## Description

`struct_to_dict.py` defines `struct_to_dict(s)`, which reads the `_fields_` of a ctypes `Structure` and returns a dictionary of field names and values. The file also includes a short example using a `Point` structure.

## Features

- Converts a ctypes `Structure` to a dictionary
- Uses field names as dictionary keys
- Works with any ctypes `Structure`
- No external dependencies (uses the standard library `ctypes` module)

## Requirements

- Python 3

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   ```

2. Navigate to the project directory:

   ```bash
   cd <your-repo-name>
   ```

No additional packages need to be installed.

## Usage

Run the script from your terminal:

```bash
python struct_to_dict.py
```

The script creates a `Point` structure and prints it as a dictionary.

## Example

```python
from ctypes import Structure, c_int, c_float

class Point(Structure):
    _fields_ = [("x", c_int), ("y", c_int), ("z", c_float)]

def struct_to_dict(s):
    return {name: getattr(s, name) for name, _ in s._fields_}

p = Point(1, 2, 3.5)
print(struct_to_dict(p))
```

Output:

```
{'x': 1, 'y': 2, 'z': 3.5}
```

## Project Structure

```
.
├── struct_to_dict.py
├── README.md
└── audit.md
```

