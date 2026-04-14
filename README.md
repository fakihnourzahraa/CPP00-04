# CPP00-04

A progressive deep-dive into C++ Object-Oriented Programming through the 42 curriculum, covering everything from basic I/O to abstract classes and interfaces.

---

## Overview

This repository contains exercises from **CPP Modules 00–04**, each building on the last to introduce core C++ OOP concepts unavailable in C. All code is compiled with `-std=c++98 -Wall -Werror -Wextra`.

---

## Module Breakdown

### CPP00 — Namespaces, Classes, Member Functions, I/O
- **ex00 — Megaphone**: Command-line argument parser that uppercases all input strings.
- **ex01 — Phonebook**: An interactive phonebook app with up to 8 contacts. Demonstrates class design, `std::cin`/`std::cout`, and formatted table output with `<iomanip>`.

---

### CPP01 — Memory Allocation, References, Pointers to Members
- **ex00 — BraiiiiiiinnnzzzZ**: Stack vs. heap zombie allocation. Introduces `new`/`delete` and destructor logging.
- **ex01 — ZombieHorde**: Array allocation with `new[]`/`delete[]` for a horde of zombies sharing one name.
- **ex02 — HI THIS IS BRAIN**: Demonstrates that a pointer and a reference to the same variable share the same memory address.
- **ex03 — Unnecessary Violence**: `HumanA` holds a `Weapon` by **reference** (always armed); `HumanB` holds one by **pointer** (optionally armed). Illustrates when to use each.
- **ex04 — Sed is for Losers**: File-based string replacement using `std::ifstream`/`std::ofstream` — no `std::string::replace` allowed.
- **ex05 — Harl 2.0**: Complaint logger using an **array of member function pointers** to dispatch log levels.
- **ex06 — HarlFilter**: Same Harl class but dispatched via a `switch` with fall-through — logs from a given level and all above it.

---

### CPP02 — Ad-hoc Polymorphism, Operator Overloading, Orthodox Canonical Form
- **ex00**: Bare-bones `Fixed` class in **Orthodox Canonical Form** (default constructor, copy constructor, copy assignment operator, destructor).
- **ex01**: `Fixed` gains `int` and `float` constructors, `toInt()`, `toFloat()`, and a stream insertion operator `<<`.
- **ex02**: Full `Fixed` point arithmetic — all six comparison operators, four arithmetic operators (`+`, `-`, `*`, `/`), pre/post increment and decrement, and static `min`/`max` functions.

---

### CPP03 — Inheritance
- **ex00 — ClapTrap**: Base class with `attack`, `takeDamage`, and `beRepaired`, tracking hit points and energy points.
- **ex01 — ScavTrap**: Inherits `ClapTrap`, overrides `attack`, adds `guardGate`. Demonstrates proper constructor/destructor chaining.
- **ex02 — FragTrap**: Another `ClapTrap` child with different stats and `highFiveGuys`.
- **ex03 — DiamondTrap**: Multiple inheritance from `ScavTrap` and `FragTrap`. Uses **virtual inheritance** to solve the diamond problem. Has its own `name` separate from `ClapTrap::name`.

---

### CPP04 — Subtype Polymorphism, Abstract Classes, Interfaces
- **ex00 — Polymorphism**: `Animal` base class with a `virtual makeSound()`. `Dog` and `Cat` override it. `WrongAnimal`/`WrongCat` demonstrate what breaks without `virtual`.
- **ex01 — Brain**: `Dog` and `Cat` now own a heap-allocated `Brain` (100 ideas). Deep copy is enforced in copy constructors and assignment operators.
- **ex02 — Abstract Animal**: `Animal::makeSound()` becomes pure virtual (`= 0`), making `Animal` an abstract class that cannot be instantiated directly.
- **ex03 — Interfaces & MateriaSource**: Full RPG-style spell system. `AMateria` is an abstract base; `Ice` and `Cure` implement it. `ICharacter` and `IMateriaSource` are pure-interface classes. `Character` manages a 4-slot inventory with proper deep copy, and unequipped materias are tracked in a dynamic disposal array to prevent memory leaks.

---

## Key Concepts Covered

| Concept | First Introduced |
|---|---|
| Classes, access specifiers | CPP00 |
| `new` / `delete`, stack vs. heap | CPP01 |
| References vs. pointers | CPP01 |
| Member function pointers | CPP01 |
| Orthodox Canonical Form | CPP02 |
| Operator overloading | CPP02 |
| Fixed-point arithmetic | CPP02 |
| Single inheritance | CPP03 |
| Multiple & virtual inheritance | CPP03 |
| Virtual functions & vtables | CPP04 |
| Pure virtual / abstract classes | CPP04 |
| Interfaces (pure abstract classes) | CPP04 |
| Deep copy with heap members | CPP04 |

---

## Building & Running

Each exercise has its own `Makefile`. From within any exercise directory:

```bash
make        # compile
./binary    # run
make clean  # remove .o files
make fclean # remove .o files + binary
make re     # fclean + all
```

---

*Made with lots of coffee and debugging at 42 Beirut*