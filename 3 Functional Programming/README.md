### Paradigm
- How to let others pick up my code and add features? How to structure your code?
  - Functional Programming
  - Object-Oriented Programming

### Pure Function
- With the same input, pure function always return the same output
- No side-effect which means it won't change any external state(return deep copied value for instance)
- `The only consequence is determined by the return value.`

### Some Code Reuse
- What are we doing when we go create parameters with function?
  - Modulize/Generalize things
- What is the essence of `parameter`?
  - **Placeholder**
- Placehold what?
  - `Attributes` (Attribute)
  - `Behaviour` (Function)
  - `Attributes + Behaviour` (Class)
- Parameters are used when you **call** the function `rather than when you define the function`.
- Generics are declared when you **initialize** the class `rather than when you define the class`.

### Try to define Code-Reuse
> Determine `module` inside a `module` outside the `definition` stage where module maybe `attribute`,`behaviour` or `Entity`.

### High-Order Function
- Take a `function` as argument or return another `function`
  - placehold the `functionality`
- Just act like a `container` function

### Coincidence
- ABC:
  - Attribute
  - Behaviour
  - Class
- TV:
  - Type (Ckass)
  - Value (Attribute)
  - Time: (Function)

# Core
- `Dynamic` is about `time`.