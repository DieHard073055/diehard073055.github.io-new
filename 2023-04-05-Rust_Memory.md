## Rust Study Notes

### Ownership

- Ownership system ensures memory safety without garbage collection
- Three core concepts: ownership, borrowing, and lifetimes
- Variables have ownership, and moving ownership can invalidate previous references
- Borrowing allows sharing ownership temporarily
- Lifetimes track how long a borrow is valid

### Borrowing and References

- Two types of references: shared (&) and mutable (&mut)
- Shared references allow multiple readers, mutable references allow a single writer
- Borrow checker enforces rules to prevent data races

### Lifetimes

- Lifetimes ensure references remain valid while in use
- Annotated with syntax like: 'a
- Explicit lifetimes required in some cases (e.g., for structs with references)
- Sometimes lifetimes can have "holes" when a reference is moved and then reassigned

### Generic Lifetimes

- Types can be generic over lifetimes, just as they can be over types
- Useful for types that store references or return references with specific lifetimes
- Multiple lifetimes may be necessary in some cases, but often just complicate type signatures

### Lifetime Variance

- Variance determines when a subtype can be used in place of a supertype
- Three kinds: covariant, invariant, and contravariant
- Covariant: subtypes can be used in place of the type (e.g., &'a T)
- Invariant: exact type must be provided (e.g., &mut T)
- Contravariant: reversed relationship between sub- and supertypes (e.g., Fn(T) is contravariant in T)

### Summary

- Understanding Rust's memory and ownership model is crucial
- Lifetimes and borrowing help ensure memory safety
- Variance is important when working with generic lifetime parameters

