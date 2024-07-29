---
title: Odin to C++ Conversion
Description: I've been seeing that raylib is popular among odin developers. Here are my living notes on how to convert it to C++
Created: ""
cssclasses: 
tags:
  - Godot
  - Programming
  - Raylib
---
I've noticed a lot of similarities with GDScript and odin. For example, GDscript seems like they got odin and just python-ified it. 

> ***python-ification***
> The act of making something look like python.

## Basic Syntax Differences

### Function Definitions

**Odin:**


```odin
func add(a: int, b: int) -> int {
    return a + b;
}
```

**C++:**
```cpp
int add(int a, int b) {
    return a + b;
}
```

### Variable Declarations

**Odin:**
```odin
x: int = 10;
```

**C++:**
```cpp
int x = 10;
```

### Constants

**Odin:**
```odin
MY_CONST: int = 100;
```

**C++:**
```cpp
const int MY_CONST = 100;
```

## Control Flow

### If Statements

**Odin:**
```odin
if x > 0 {
    // do something
}
```

**C++:**
```cpp
if (x > 0) {
    // do something
}
```

### For Loops

**Odin:**
```odin
for i in 0..10 {
    // do something
}
```

**C++:**
```cpp
for (int i = 0; i < 10; i++) {
    // do something
}
```

### While Loops

**Odin:**
```odin
for x < 10 {
    // do something
}
```

**C++:**
```cpp
while (x < 10) {
    // do something
}
```

## Data Structures

### Arrays

**Odin:**
```odin
arr: [5]int;
```

**C++:**
```cpp
int arr[5];
```

### Slices

**Odin:**
```odin
slice: []int;
```

**C++:**
```cpp
std::vector<int> slice;
```

### Structs

**Odin:**
```odin
Rectangle :: struct {
    width: int,
    height: int,
}
```

**C++:**
```cpp
struct Rectangle {
    int width;
    int height;
};
```

## Functions and Methods

### Method Definitions

**Odin:**
```odin
func (r: Rectangle) area() -> int {
    return r.width * r.height;
}
```

**C++:**
```cpp
struct Rectangle {
    int width;
    int height;

    int area() {
        return width * height;
    }
};
```

### Updating a Player Example

**Odin:**
```odin
func update_player(player: ^Player) {
    player.position += player.velocity * time.delta;
}
```

**C++:**
```cpp
void update_player(Player* player) {
    player->position += player->velocity * time.delta;
}
```

## Object-Oriented Programming

### Classes

**Odin:**
```odin
Player :: struct {
    position: Vector2,
    velocity: Vector2,
}

func (p: Player) move() {
    p.position += p.velocity;
}
```

**C++:**
```cpp
class Player {
public:
    Vector2 position;
    Vector2 velocity;

    void move() {
        position += velocity;
    }
};
```

## Memory Management

### New and Delete

**Odin:**
```odin
p := new(Player);
```

**C++:**
```cpp
Player* p = new Player();
```

### Deleting an Object

**Odin:**
```odin
delete(p);
```

**C++:**
```cpp
delete p;
```

## Namespaces and Modules

### Namespaces

**Odin:**
```odin
package main
```

**C++:**
```cpp
namespace MyNamespace {
    // code
}
```

## Error Handling

### Error Handling

**Odin:**
```odin
value, err := some_function();
if err != nil {
    // handle error
}
```

**C++:**
```cpp
try {
    value = some_function();
} catch (const std::exception& e) {
    // handle error
}
```

## Templates and Generics

### Generics

**Odin:**
```odin
Stack :: struct(T) {
    data: []T,
    // methods
}
```

**C++:**
```cpp
template <typename T>
struct Stack {
    std::vector<T> data;
    // methods
};
```