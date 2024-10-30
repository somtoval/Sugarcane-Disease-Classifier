- artifacts_entity: This is what the component will give out after processing, it will be stored in artifacts directory for the next component to use.
- config_entity: connects what the component needs and what the answer is to give the component, and this is how the component expects
- constants: have the answer for each component




















In Python, dataclasses are a feature introduced in Python 3.7 that simplifies the creation of classes used primarily for storing data. They help reduce boilerplate code by automatically generating methods like __init__(), __repr__(), __eq__(), and others based on class attributes. Essentially, they are a concise and clean way to define "plain old data objects."

Why Use dataclasses?
- Reduces Boilerplate Code: You don’t have to manually write common methods like __init__, __repr__, __eq__, etc.
- Easy to Use: You can define classes intended for storing data with less effort.
- Type Annotations: They work well with type hints, making your data structures clearer.

How to Use dataclasses:
To create a dataclass, use the @dataclass decorator and define your class attributes. Here's a simple example:

from dataclasses import dataclass

@dataclass
class Person:
    name: str
    age: int
    city: str

In this example, Person is a dataclass with three fields: name, age, and city.

When you create an instance of this class, Python automatically generates an initializer (__init__) for you:

person = Person(name="John Doe", age=30, city="New York")
print(person)  # Output: Person(name='John Doe', age=30, city='New York')

