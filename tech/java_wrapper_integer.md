---
up:
  - "[[java]]"
---
# JAVA -> DATA TYPES -> INTEGER
## SUMMARY
> [!summary]
> Integer wraps the int primitive. It includes a caching range and parse methods.

## THEORY
Integer caching for values −128 to 127 prevents unnecessary object creation. Autoboxing is convenient, but large repetitive use can still harm performance. Checking Integer equality with == only works reliably within cached range.

## QUESTIONS
#flashcards/java

What does Integer.valueOf() do?
?
Uses the cache if the value is in the range, otherwise creates a new object.

Why can == be misleading for two Integer objects?
?
== compares object references, which may differ outside the cache range.

How do you properly compare Integer values?
?
Use .equals() for object equality.
