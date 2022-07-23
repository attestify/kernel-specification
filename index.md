# Attestify - Kernel Specification

The kernel specification defines the interfaces and expected behaviors for the primitive components for Attestify.

TODO - Explain how kernel, use case, and infrastructure work.

## Value Objects

* All kernel objects are immutable
* All methods return a copy of an object
* Every object must have an Equals(...) method which returns a bool

### URI

#### Top Level Domain

![Top Level Domain Image](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/top-level-domain.svg)