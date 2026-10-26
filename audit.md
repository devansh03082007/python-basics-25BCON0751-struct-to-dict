# README Claims Audit

Audit of the claims in `README.md` against the actual code in `struct_to_dict.py`.

| # | Claim | Verdict | Evidence from code |
|---|---|---|---|
| 1 | Converts a ctypes `Structure` to a dictionary | Supported | `{name: getattr(s, name) for name, _ in s._fields_}` |
| 2 | Field names become dictionary keys | Supported | `name` comes from `_fields_` |
| 3 | Works with any ctypes `Structure` | Supported | Reads `_fields_`, which every `Structure` defines |
| 4 | Supports nested structures | Not Supported | `getattr` returns the nested ctypes object as-is, not a converted dict |
| 5 | Supports dataclasses, namedtuples and other struct types | Not Supported | Only `s._fields_` is used, which exists only on ctypes types |
| 6 | Validates input / raises a clear error for invalid objects | Not Supported | Passing a non-ctypes object raises `AttributeError` on `_fields_` |
| 7 | Includes a working example | Supported | `Point` class with `p = Point(1, 2, 3.5)` |
| 8 | Example output is `{'x': 1, 'y': 2, 'z': 3.5}` | Supported | Matches `print(struct_to_dict(p))` |
| 9 | Can be imported without side effects | Not Supported | No `if __name__ == "__main__":` guard, so importing creates `Point` and prints the dict |
| 10 | No external dependencies | Supported | Only `ctypes`, which is in the standard library |
| 11 | Requires Python 3 | Supported | Code runs on Python 3 |
| 12 | Project structure includes `README.md` and `LICENSE` | Unverified | Cannot be confirmed from the code |
| 13 | MIT License | Unverified | Not stated in the code |

## Summary

- Not Supported: claims 4, 5, 6 and 9
- Unverified: claims 12 and 13
- All other claims are Supported
