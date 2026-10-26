# python-basics-25BCON0751-struct-to-dict
this is a python program to convert structured data into dictionaries 
# struct_to_dict

A simple Python helper that converts a ctypes `Structure` into a dictionary.

## Description

This project provides a lightweight utility for turning a ctypes `Structure` into a standard Python dictionary. The `struct_to_dict.py` script reads the structure's fields and returns their names and values as key-value pairs, which makes the data easy to print, serialize or inspect.

## Features

- Converts a ctypes `Structure` to a dictionary
- Uses field names as dictionary keys
- Works with any ctypes `Structure`
- Supports nested structures
- Raises a clear error for invalid input
- Importable as a module without side effects
- No external dependencies

## Requirements

- Python 3.6 or higher

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

To use the function in your own code:

```python
from struct_to_dict import struct_to_dict

print(struct_to_dict(my_structure))
```

## Example

```python
from ctypes import Structure, c_int, c_float

class Point(Structure):
    _fields_ = [("x", c_int), ("y", c_int), ("z", c_float)]

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
└── LICENSE
```

## Contributing

Contributions, issues, and feature requests are welcome. Feel free to open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
