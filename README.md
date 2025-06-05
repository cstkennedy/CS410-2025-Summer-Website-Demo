# Example GitHub Pages Site

# Quick Links

  - [GitHub Pages Site](https://cstkennedy.github.io/cs410-2025-Spring-Pages-Example/)
  - [GitHub Repository](https://github.com/cstkennedy/cs410-2025-Spring-Pages-Example)


## GitHub Pages

  - [GitHub Flavor Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)


## HTML & CSS Reference

  - [HTML](https://www.w3schools.com/html/default.asp)
  - [CSS](https://www.w3schools.com/css/default.asp)
  - [Bootstrap](https://www.w3schools.com/bootstrap5/index.php)


## JavaScript Reference

T.B.W.


# Notes

By default `README.md` will be used as your GitHub Pages site's `index.html`
(i.e., landing/home page).


## Code Snippets

Code snippets are denoted with triple backticks followed by the language.

```rust
#[derive(Debug, Error, PartialEq)]
pub enum StrategyError {
    #[error("{:?}", .0)]
    ParseError(#[from] std::num::ParseIntError),
    #[error("{:?}", .0)]
    BoardError(#[from] BoardError),
    #[error("{:?}", .0)]
    OutOfMovesError(String),
}
```

```python
 _KNOWN_SHAPES: dict[str, Callable[[None | list[float]], Shape]] = {
    # ...
}
```

## Table

Markdown supports tables.

| Description                                                               | Rust                         |
| :----                                                                     | :----                        |
| Create a "default" or "empty" object                                      | Default trait                |
| Create a "default" or "empty" object                                      | `new()`                      |
| Create an identical (yet distinct) copy of an object                      | `Clone` trait                |
| Define resources that need to be "closed" before deallocation             | `Drop` trait                 |
| Access a data member                                                      | Accessors (Getters)          |
| Update a data member                                                      | Mutators (setters)           |
| Compare two objects                                                       | `std::cmp::PartialEq` trait  |
| Assign an ordering to two objects.                                        | `std::cmp::PartialOrd` trait |
| Compute a number that can be used to store an object in a `dict` or `set` | `std::hash::Hash` trait      |
| Generate a human readable string for output                               | `std::fmt::Display` trait    |
| Generate a string for debugging output                                    | `std::fmt::Debug` trait      |
| Allow read-only access to entries in a collection                         | `iter()`                     |
| Allow read-and-write access to entries in a collection                    | `iter_mut()`                 |



