# CS106L Fall 2022 Study Notes by Jinyi Zhou

## Lecture 1

C++ is a **statically typed** (everything with a name is given a type before runtime) language.

***Dynamically typed**: everything with a name (variables, functions, etc) is given a type at **runtime** based on the thing’s current value.*

**Overloading**: define two functions with the same name but different types.

**Struct**: a group of named variables each with their own type. A way to bundle different types together.

```cpp
struct Student {
    std::string name;
    std::string state;
    int age;
}

Student s;
s.name = "Sarah";
s.state = "CA";
s.age = 21;

// is the same as...

Student s = {"Sarah", "CA", 21};
```

```std::pair```: an STL built-in struct with two
fields of any type. It is a template -- you specify the types of the fields inside <> for each pair object you make.

```cpp
std::pair<bool, Student> lookupStudent(std::string name) {
    Student blank;
    if (notFound(name)) return std::make_pair(false, blank);
    // to avoid specifying the types of a pair,
    // use std::make_pair(field1, field2)
    Student result = getStudentWithName(name);
    return std::make_pair(true, result);
}
    std::pair<bool, Student> output = lookupStudent(“Julie”);
```

```auto```: keyword used in lieu of type when declaring a variable, tells the compiler to deduce the type.

**Stream**: an abstraction for input/output. Streams
convert between data and the string representation of data.