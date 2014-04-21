# Rust

*Brandon Mills, Paul Tela, Adam Wheeler*

### Sample test questions
1. Question: What is the type of x after the following declaration?

    ```
    let x = 3.14;
    ```

    Answer: `f64`

2. Question: What is the output of the following code?

    ```
    let x = 0;
    while x < 10 {
        let x = x + 1;
    }
    println!("{}", x);
    ```

    Answer: There is no output since the code never terminates.  The `x` in the guard of the `while` is different from the `x` declared inside the loop.

3. Question: Fix the compile error in the following snippet, assuming `num` is of type `i32`:

    ```rust
    match num {
        0     => println!("zero"),
        1 | 2 => println!("one or two"),
        3..10 => println!("three to ten")
    }
    ```

    Answer: `match` is exhaustive; it requires that all possible values be considered. Add `_ => println!("something else")` at the end of the `match`.

4. Question: Which of the following is an invalid?

    A:
    ```rust
    enum Color {
        Red   = 0xff0000,
        Green = 0x00ff00,
        Blue  = 0x0000ff
    }
    ```

    B:
    ```rust
    enum Point {
        x: f64,
        y: f64
    }
    ```

    C:
    ```rust
    enum Shape {
        Circle(Point, f64),
        Rectangle(Point, Point)
    }

    impl Shape {
        fn area (&self) -> f64 {
            match *self {
                Circle(_, size) => f64::consts::PI & size & size,
                Rectange(Point {x, y}, Point {x: x2, y: y2}) => (x2 - x) * (y2 - y)
            }
        }
    }
    ```

    Answer: B. What is shown is a `struct`.

5. Question: Which of the following is not a valid pointer type?

    - A. Owned
    - B. Managed
    - C. Garbage Collected
    - D. Reference/Borrowed

    Answer: C.  Managed pointers are, however, garbage collected.

6. Question: True or False: References are safety checked at runtime, making them significantly more expensive to use than C pointers.

    Answer:  False.  References are the exact same as C pointers at runtime.  All safety checks are performed at compile time.
