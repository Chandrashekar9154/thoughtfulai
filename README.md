# Package Sorting Challenge

This is a small program that decides how a package should be dispatched based on its size and weight.

## Rules

A package is:
- **Bulky** if:
  - Its volume (Width × Height × Length) is at least 1,000,000 cm³, or
  - Any of its dimensions is 150 cm or more.
- **Heavy** if:
  - Its mass is 20 kg or more.

Dispatch rules:
- **STANDARD** → Not bulky and not heavy.
- **SPECIAL** → Bulky or heavy (but not both).
- **REJECTED** → Both bulky and heavy.

## Function


def sort(width, height, length, mass):
    volume = width * height * length
    bulky = volume >= 1_000_000 or width >= 150 or height >= 150 or length >= 150
    heavy = mass >= 20
    if bulky and heavy:
        return "REJECTED"
    elif bulky or heavy:
        return "SPECIAL"
    else:
        return "STANDARD"

