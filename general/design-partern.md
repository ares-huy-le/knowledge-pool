# Design partern

## Table of content

### Object creation

	- Prototype
	- Factory method
	- Abstract factory
	- Builder
	- Singleton

### Interface adaption
	
	- Adapter
	- Bridge
	- Facade
	
### Decoupling of object

	- Mediator
	- Observer

### Abstract collection

	- Composite
	- Iterator

### Behaviral extension

	- Visitor
	- Decorator
	- Chain of Responsibility

### Algorithm encapsulation

	- Template method
	- Strategy
	- Command

### Performance and Object Access

	- Flyweight
	- Proxy

### State of object

	- Memento

## Detail

### Creational pattern

#### Intent

Create object in many ways and structures. Theu control the process of creating object.

#### Abstract factory

##### Intent

- Provide an interface to create 	related or dependent objects without specifying their concrete object.

#### Factory method

- Provide an interface to create objects of one specific concrete object.

##### Different with Abstract factory

- Abstract factory have several factory classes.

#### Prototype

- Create an object from a blueprint of class.
- Clone an object

##### In objective-c

- NSCopying

#### Builder

- Focus on constructing a complex object step by step.
- Often build a composite object.
- A common input, many outputs

#### Singleton

- Only one object of class was created.

### Structural patterns

#### Adapter

- Convert an interface of a class into another interface client expect.
- Wrap an existing class with a new interface.

#### Bridge

- Decouple two classes.

* Different between Adapter and Bridge:
	- Adapter makes things work **after** they're designed.
	- Bridge makes them work **before** they are designed.

#### Composite

- Compose objects into a hierarchive structure.

#### Decorator

- Add behavior or state into individual objects at runtime.
- Tips:
	- Adapter provides different interface. Decorator provides enhanced interface.

#### Facade

- Provide a unified interface to a set of interface in a subsystem.
- Wrap a complicated subsystem with a simpler interface.

#### Flyweight

- Reuse object

#### Proxy

- A stand-in / representation for other heavy object.

### Behavioral patterns

#### Chain of responsibility

- Send a method to a chain of object, if object can handle, request will be launch, unless request will be forwarded to another object in chain.

#### Command

- Encapsulate a request as an object.
- To store, delay, resend or reroute message.
- To queue, specify, excute message at specific time.

#### Iterator

- To have a same way to traverse over various collection what have different data structure.
- Reuse the operator algorithms when traverse over different container type - data structure
- Use for composite pattern

#### Mediator

- Define an object that encapsulate how the set of object interact.

#### Memento

- Capture and externalize an object's internal state so that the object can be returned to this state later. 

#### Observer

- Define one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

#### Strategy

- Define a family of algorithms, encapsulate each one, and make them interchangeable. Strategy lets the algorithm vary independently from the client that use it.
- Encapsulate the algorithms in a object.
- Decrease the switch / case, if / else when choose the specific algorithm.
- Don't break open - closed principle.

#### Template method

- Define the skeleton of an algorithm in an operation, deferring some steps to client subclasses. Template method lets subclasses redefine certain steps of an algorithm without changing the algorithm's structure.
- Base class declares algorithm 'placeholders', and derived classes implement the placeholders.

#### Visitor

- Represent an operation to be performed on the elements of an object structure. Visitor lets you define a new operation without changing the classes of the elements on which it operates.
