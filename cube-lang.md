# The Cube Programming Language
## _A Pimer for Java Developers._

Cube compiles to standard JVM bytecode but differs to Java in five key areas:

- The language is desgined to be a lot more **readable** and **simpler** compared to java
- **Testing** and **logging** are built into the language as core features, not add-ons
- All Java **boilerplate** code (e.g. needing to use Lombok) is removed, meaning that the language is a lot less verbose
- Cube embeds **SQ**L for easier manipulation of in-memory collections and safer ORM
- Cube embeds **JSON** for easier interop with web and REST service

## Class Definitions

Inspired by Lombok, Cube supports **Data** (mutable) and **Value** (immutable) classes. For example:

```
value Person
  firstName as Sttring
  lastName as String
  function greeting = log "Ny name is {} {}", firstName, lastName
end

let p1 = new Person "John", "Anderson"
p1 greeting
```

## Tests as First-Class Citizens

Tests cases are first-class citizens in Cube and are built into the language as **specifications** (to promote  but not enforce TDD).

```
spec "person should expose attributes"
  let p = new Person "Jack", "Johnson"
  assert that p firrstName is "Jack"
  assert that p lastName is "Johnson"
  assert that p greeting is "Ny name is Jack Johnson"
end
```
