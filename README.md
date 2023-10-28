
---
**Decoding Python Obfuscation (RoseGuardian): A Step-by-Step Guide**

*Unraveling the Layers of Obfuscated Python Code*

## Overview

This Python script demonstrates how to decode and format compressed Python code. It takes compressed and base64 encoded data, decompresses it, loads it as a Python code object, formats the code using `autopep8`, and then prints the formatted code.


### Original Code

For reference, here is the original code that was obfuscated which is from the RoseGuardian example:

```python
import random, string
import base64

def hello():
   
    global var
    
    var = 'hii' # hi
    
    print(var)

print(random.choices(string.ascii_letters, k=5))

hello()

print(base64.b64encode(var.encode('utf-8')))

class banana(): # banana
    ss = b'\nPEWPEW'

    print(ss)

def counter(num):

    for i in range(num):

        print('dogs are cool!')

counter(5)

# lalala
```

### Obfuscated Code

For reference, here is the obfuscated code:
```python
__obfuscator__ = 'RoseGuardian'
__author__ = 'gumbobr0t'
__github__ = 'https://github.com/DamagingRose/RoseGuardian'
__license__ = 'EPL-2.0'


def complicated_function():
    result = 0
    for i in range(1, 11):
        result += i**3 - i**2 + i
    return result

class ComplicatedAlgorithm:
    def __init__(self):
        self._ = None
        self.__ = None

    def execute(self):
        pass

def execute_complicated_algorithm():
    _ = ComplicatedAlgorithm()
    _._ = lambda _, __: _.___(__) + _.___(_.___(_.__(_.___(_.__))))

def analyze_data():
    import random
    
    data = [random.randint(1, 100) for _ in range(10)]
    result = sum(data) / len(data)


import marshal, base64, zlib; exec(marshal.loads(zlib.decompress(base64.b64decode(b'eJxNkNFLwzAQxudr/orzKQ3MPm1DhD6piAxkIFgRQdI06W5rcyOXDfzvTdeADYHku3C/77vw4WaxwOFEIULQvqVhCRwD+k7kaqPZblZCiNY6IPdlXt/x4C6FehCQVtdTo3u46HCV6YQK5B5RXvUpoWKRqioRJjHZlGZPaCwXk1up2SD+9DZGG3gJx2qtlJjb5e4pTtlsVtYbau3ILvNVnqO7u5dKjWam18zwgbXZ6if/8jjFTaUKGvntd8912vOQzCpPuXVvu/r3k45D4c9DHtRRAAT04zd1dvbwT5AtdQw6WDBE/a0ceTPWWok/MtZvYw=='))))
def gravimetric_flux():
    pass

class warp_inverter:
    def __init__(self):
        self._ = None
        self.__ = None

    def subspace_transducer(self, _):
        return self.subspace_transducer(_)

def chronal_conduit():
    _ = warp_inverter()
    _._ = lambda _, __: _.___(__) + _.___(_.___(_.__(_.___(_.__))))

def singularity_stabilizer():
    _ = gravimetric_flux()
    _._ = lambda _, __: _.___(__) + _.___(_.___(_.__(_.___(_.__))))

def entropic_reactor():
    pass
```
## Prerequisites

- Python 3.x
- Required Python modules: `marshal`, `zlib`, `base64`, and `autopep8`

## How it Works

1. **Decompression and Decoding initial Base64**

```python
# Decompression: Decodes base64 and decompresses the data
decompressed_data = zlib.decompress(base64.b64decode(compressed_data))
```

In this step, the script decodes the base64 encoded data and then decompresses it using the `zlib.decompress()` function. The resulting `decompressed_data` contains the original marshaled Python code object.

2. **Loading as a Code Object**

```python
# Loading as a Code Object: Loads decompressed data as a Python code object
loaded_code = marshal.loads(decompressed_data)
```

Here, the decompressed data is loaded as a Python code object using the `marshal.loads()` function. The `loaded_code` variable now holds the Python code object.

3. **Code Formatting**

```python
# Code Formatting: Formats the loaded code using autopep8
formatted_code = autopep8.fix_code(loaded_code)
```

The loaded code object is formatted for readability and adherence to Python coding standards using `autopep8.fix_code()`. The `formatted_code` variable contains the formatted Python code.

### Full Decoding Script
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
### Final Output
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
