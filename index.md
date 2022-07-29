# Attestify - Kernel Specification

The kernel specification defines the interfaces and expected behaviors for the primitive components for Attestify. This specification is independent of any specific language implementation. It describes how the kernel objects must operate regardless of the implementing programming language.

The Attestify kernel is inspired by the concept of a shared kernel from [Domain Driven Design](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215). The shared kernel are overlapping contexts that two-or-more domains rely upon.  

We've shortened the name to just ***kernel***. Following the same concept as the shared kernel, these are objects and interfaces that are shared amongst multiple context.  These objects represent the primitives so the Attestify domain.

## Kernel Concepts

* Value Objects
* Entity

### Value Objects

Also based upon the concept of a [value object](https://learning.oreilly.com/library/view/domain-driven-design-tackling/0321125215/ch05.html) from [Domain Driven Design](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215).

Chapter 5 of the book has some great excerpts.  Here are our favorite:

* "Many objects have no conceptual identity. These objects describe some characteristic of a thing."
* "An object that represents a descriptive aspect of the domain with no conceptual identity is called a VALUE OBJECT. VALUE OBJECTS are instantiated to represent elements of the design that we care about only for what they are, not who or which they are."

Additional attributes of the Attestify kernel value objects are:

* All kernel objects are immutable
* All methods return a copy of an object
* Every object must have an Equals(...) method which returns a bool

#### Standard Behaviors

##### Equals(...)

All value objects have an Equals(...) behavior which compares the values for one instance of a given value obeject to another instance of the same type value object. 

### Entity - *TODO*

## Kernel Elements

### URI

**Namespace** - io.attestify.kernel.uri

The URI (Uniform Resource Identifier) kernel package contains the objects which align to the [RFC3986 - Uniform Resource Identifier: General Syntax](https://datatracker.ietf.org/doc/html/rfc3986) specification.

#### Host

**Namespace** - io.attestify.kernel.uri.host

Host is the URI host as defined in [RFC3986 Section 3.2.2 - Host](https://datatracker.ietf.org/doc/html/rfc3986#section-3.2.2)

Limitations
* Only has functionality for registered name.
* Does not have functionality for IP-literal or IPv4address

Interface
* Value() - Returns a string representation of the host
* HostType() - Returns a string representation for the type of host
  * Host types
    * ***reg-name*** - registered Name
    * ***ip*** - IP-literal
    * ***ipv4*** - IPv4Address
    
Constructors
* (RegisteredName registeredName) - Constructs and object from a RegisteredName object from the URI kernel package.

![Host Class Diagram](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/host.svg)

#### Registered Name

**Namespace** - io.attestify.kernel.uri.registered-name

An implementation of Registered Name by [RFC1034 Section 3.5](https://datatracker.ietf.org/doc/html/rfc1034#section-3.5) and [RFC1123 Section 2.1](https://datatracker.ietf.org/doc/html/rfc1123#section-2.1).

Interface
* Value() - Returns a string representation of the registered name.

Constructors
* (String topLevelDomain, String domainName) - Constructs object from a string representation of a top level domain and a domain name.
* (String registeredName) - Constructs and object from a string representation of a registered name

![Registered Name Class Diagram](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/registered-name.svg)

#### Domain Name

**Namespace** - io.attestify.kernel.uri.domain-name

![Domain Name Class Diagram](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/domain-name.svg)

#### Top Level Domain

**Namespace** - io.attestify.kernel.uri.top-level-domain

![Top Level Domain Class Diagram](https://raw.githubusercontent.com/attestify/kernel-specification/main/diagrams/uri/top-level-domain.svg)