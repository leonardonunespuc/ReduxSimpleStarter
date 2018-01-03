# Undo Manager

Component to fulfill the task of registering, undoing and redoing changes to some text document.

## Getting Started

The component has an **UndoManagerImpl** class that makes use of a Buffer and two Stacks, one for Undo and the other for the Redo change operations.
The two Stacks combined will never grow larger then the Buffer size.
The first element of the Undo Stack is removed whenever the Buffer size is reached.

When a new change is registered all Redos will not be available anymore. 
The Redo Stack will have all the elements removed.

The Undo operation removes one change from the Undo Stack, revert the change on the document and then add the change to the Redo Stack.
The Redo operation does the inverse, it removes one change from the Redo Stack, apply the change on the document and then add the change to the Undo Stack.

### Prerequisites

Install the latest stable version of Java and Maven.


## Running the tests

The following command can be used to run the tests using Maven.

```
> mvn test
```

After running the tests a Code Coverage report is generated using JaCoCo library.

Report path:
undo-manager\target\site\jacoco\index.html


## Built With

* [Maven](https://maven.apache.org/) - Dependency Management
* [JUnit](http://junit.org/junit4/) - Simple framework to write repeatable tests
* [Mockito](http://site.mockito.org/) - Mocking framework for unit tests
* [JaCoCo](http://www.eclemma.org/jacoco/trunk/index.html) - JaCoCo is a free Java code coverage library

