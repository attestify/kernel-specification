# Attestify - Kernel Specification

The kernel specification defines the interfaces and expected behaviors for the primitive components for Attestify.

TODO - Explain how kernel, use case, and infrastructure work.

## Value Objects

* All kernel objects are immutable
* All methods return a copy of an object
* Every object must have an Equals(...) method which returns a bool

### URI

#### Host

![Host Class Diagram](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/host.svg)

#### Registered Name

![Registered Name Class Diagram](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/registered-name.svg)

#### Domain Name

![Domain Name Class Diagram](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/domain-name.svg)

#### Top Level Domain

![Top Level Domain Class Diagram](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/top-level-domain.svg)