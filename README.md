# Decode-RoseGuardian
Python Decode for RoseGuardian
---

# Python Code Documentation

## Overview

This Python script demonstrates how to decode and format compressed Python code. It takes compressed and base64 encoded data, decompresses it, loads it as a Python code object, formats the code using `autopep8`, and then prints the formatted code.

## Prerequisites

- Python 3.x
- Required Python modules: `marshal`, `zlib`, `base64`, and `autopep8`

## How it Works

### Decompression and Decoding

```python
# Decompression: Decodes base64 and decompresses the data
decompressed_data = zlib.decompress(base64.b64decode(compressed_data))
```

In this step, the script decodes the base64 encoded data and then decompresses it using the `zlib.decompress()` function. The resulting `decompressed_data` contains the original marshaled Python code object.

### Loading as a Code Object

```python
# Loading as a Code Object: Loads decompressed data as a Python code object
loaded_code = marshal.loads(decompressed_data)
```

Here, the decompressed data is loaded as a Python code object using the `marshal.loads()` function. The `loaded_code` variable now holds the Python code object.

### Code Formatting

```python
# Code Formatting: Formats the loaded code using autopep8
formatted_code = autopep8.fix_code(loaded_code)
```

The loaded code object is formatted for readability and adherence to Python coding standards using `autopep8.fix_code()`. The `formatted_code` variable contains the formatted Python code.

# Full Decoding Script
```python
import marshal
import zlib
import base64
import autopep8

# Compressed and base64 encoded data
compressed_data = b'eJxNkNFLwzAQxudr/orzKQ3MPm1DhD6piAxkIFgRQdI06W5rcyOXDfzvTdeADYHku3C/77vw4WaxwOFEIULQvqVhCRwD+k7kaqPZblZCiNY6IPdlXt/x4C6FehCQVtdTo3u46HCV6YQK5B5RXvUpoWKRqioRJjHZlGZPaCwXk1up2SD+9DZGG3gJx2qtlJjb5e4pTtlsVtYbau3ILvNVnqO7u5dKjWam18zwgbXZ6if/8jjFTaUKGvntd8912vOQzCpPuXVvu/r3k45D4c9DHtRRAAT04zd1dvbwT5AtdQw6WDBE/a0ceTPWWok/MtZvYw=='

try:
    # Step 1: Decode base64 and decompress the data
    decompressed_data = zlib.decompress(base64.b64decode(compressed_data))

    # Step 2: Load the decompressed data as a Python code object
    loaded_code = marshal.loads(decompressed_data)

    # Step 3: Format the code using autopep8
    formatted_code = autopep8.fix_code(loaded_code)

    # Step 4: Print the formatted code
    print(formatted_code)

except Exception as e:
    # Handle any exceptions that might occur during the process
    print("An error occurred:", e)


```
# Final Output
If everything went well, you should be met with something that looks like this in CLI, showing the decoded code
![image](https://github.com/autumnlikescode/Decode-RoseGuardian/assets/102363146/328ef896-203b-4262-95e9-0524378e2dc6)

## Dependencies

- [marshal](https://docs.python.org/3/library/marshal.html)
- [zlib](https://docs.python.org/3/library/zlib.html)
- [base64](https://docs.python.org/3/library/base64.html)
- [autopep8](https://pypi.org/project/autopep8/)

## Contributing

Contributions and improvements are welcome! Fork the repository, make your changes, and submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

---
