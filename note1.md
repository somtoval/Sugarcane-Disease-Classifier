1. ensure_annotations (from ensure)
- ensure_annotations is a decorator that enforces function argument type annotations. If the arguments passed to the function don’t match the specified types, an error will be raised at runtime.
- Usage: This is useful for enforcing type safety in your Python code, especially when working with larger projects where data types matter.


from ensure import ensure_annotations

@ensure_annotations
def add_numbers(a: int, b: int) -> int:
    return a + b

print(add_numbers(3, 4))  # Works fine
print(add_numbers("3", 4))  # Raises a TypeError due to type mismatch


2. Any (from typing)
- Any is a type hint that allows you to indicate that a variable or function argument can be of any type. This is useful when the type is not known or can vary.
- Usage: It's helpful when you want to write flexible, generic code where the specific data type doesn't matter.


from typing import Any

def process_data(data: Any) -> None:
    if isinstance(data, int):
        print(f"Processing an integer: {data}")
    elif isinstance(data, str):
        print(f"Processing a string: {data}")
    else:
        print(f"Processing data of type {type(data)}: {data}")

process_data(123)      # Output: Processing an integer: 123
process_data("Hello")  # Output: Processing a string: Hello
process_data([1, 2, 3]) # Output: Processing data of type <class 'list'>: [1, 2, 3]



3. ConfigBox (from python-box)
- ConfigBox is a special dictionary-like object from the python-box library that allows you to access dictionary keys as attributes using dot notation (e.g., config.key instead of config["key"]).
- Usage: It simplifies the syntax for accessing nested dictionary values, making it easier to manage configuration files or complex data structures.


from box import ConfigBox

config = ConfigBox({"app": {"name": "MyApp", "version": 2.0}})

# Accessing using dot notation
print(config.app.name)      # Output: MyApp
print(config["app"]["name"])  # Standard dictionary access still works



4. BoxValueError (from python-box)
- The BoxValueError is an exception class that is raised when there’s an issue with the value inside a Box or ConfigBox. It is similar to Python’s built-in ValueError but specifically tied to the python-box library.
- Usage: You use BoxValueError to handle errors related to invalid values within your Box objects (like an invalid key access or incorrect value format).


from box import Box
from box.exceptions import BoxValueError

config = Box({"name": "ChatGPT", "version": 1})

try:
    # This will raise BoxValueError because 'non_existent_key' doesn't exist
    print(config.non_existent_key)
except BoxValueError as e:
    print(f"Error: {e}")
















Entity tells what the component needs and what format the config should give out stuff
Config arranges what the component needs and the answers and spits it out in the Entity form