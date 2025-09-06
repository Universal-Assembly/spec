# Universal Assembly
Crossplatform Language Interoperable Bytecode Target for Crossplatform Desktop Applications

UASM Bytecode can be packaged into .orb (Open Runtime Binary) files, which function similarly to .jar files. Unlike traditional executables, .orb files are completely platform-independent. When executed, the runtime compiles them on the host system, producing optimized native code. Libraries included within the .orb are compiled into native dynamic libraries, allowing seamless integration with the users system.

## The Problem with Java Bytecode, and other JVM Languages

The JVM instruction set was designed specifically with Java’s semantics in mind: object orientation, garbage collection, checked exceptions, type safety, stack-based execution, etc.

This means the bytecode reflects Java’s design (e.g., classes, fields, methods, reference types, arrays) rather than being a "universal IR" (intermediate representation).

#

Projects like Scala, Kotlin, Clojure, JRuby, Jython all run well, but often suffer “impedance mismatch”:

- Lack of tail-call elimination hurts functional languages.

- The JVM lacks true value types (until Project Valhalla), many objects must be heap-allocated even when stack or inline storage would be more efficient.

- Generic type erasure means non-Java languages need workarounds for efficient generics.

#

If bytecode was designed from the beginning as a multi-language IR, it could:
  
- Avoid Java-specific overheads.

- Enable better code generation for other paradigms (functional, procedural, systems).

- Possibly match or beat JVM performance in more scenarios.

## Oracle Ownership of Java

Oracle’s ownership of Java gives it control over the JDK, the Java SE specifications, and the Java trademark, allowing it to dictate licensing, updates, and usage, which can lead to vendor lock-in, costly subscriptions, and legal risks for developers and enterprises.
