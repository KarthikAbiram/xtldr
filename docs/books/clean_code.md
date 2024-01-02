---
hide:
  - navigation
---
# Clean Code

My personal notes and key takeaways from the book 'Clean Code' by Robert C Martin.

!!! note "Measurement of Code Quality"
    The only valid measurement of code quality: WTFs/minute - [Thomas Holwerdia](https://www.osnews.com/story/19266/)
    
![WTFs per minute](https://www.osnews.com/images/comics/wtfm.jpg)

Learning to write clean code is more of an art that comes with experience, like learning to ride a bicycle. We need to conciously make choices to write cleaner code, reflect on 'bad choices' that we might have made. 

In a system with bad code, the productivity of the team would decreasing to a point where it reaches almost 0 and the product is dropped. Or it goes for a grand redesign, racing against time to have all features as the old system.

The old way to go fast is to keep the code as clean as possible at all times.

A programmer with 'code sense' can look at a messy module and see options and variations to make it better. Some of us are born with 'code sense' while some have to fight to acquire it.

**What is Clean Code?**

- Clean code is focused - it does one thing well.
- Clean code can be read and enhanced by a developer other than its original author.
- Code without tests is not clean.

!!! note "Time Spent on Reading Code vs Writing Code"
    There is no way to write code without reading the surrounding code. The ratio of time spent reading code versus writing code is well over 10 to 1. So, if you want to go fast, if you want to get done quickly, if you want your code to be easy to write, make it easy to read. - Robert C Martin. 

!!! note "The Boy Scout Rule"
    Leave the campground cleaner than you found it. The code has to be kept clean over time and has to be cared for, by refactoring when necessary. Example, change a variable name for the better.

## Meaningful Names
- Choose names that reveal intent - why it exists, what it does, how it is used and what is its unit. If a name requires a comment, then it does not reveal its intent.
- Avoid noninformative names like a1, a2. Instead name them appropriately, like source and destination.
- Avoid disinformation. Eg: Do not refer to a grouping of accounts as an accountList, unless its actually a list. If the container holding the accounts is not actually a list, it may lead to false conclusions.
- Avoid noise words. Eg: Data, Info.
- Distinguish similar variable names so that the reader can know the difference between the two and when to use which one.
- Use pronounceable names that you tell over a call. Eg: Avoid names like 'genymdhms' (was referring to generation date, year, month, day, hour, minute, second)
- Prioritize clarity over brevity.
- Avoid ambiguous or generic names.

!!! question
     Uncle Bob suggests to not prefix interfaces with 'I'. Reasoning: I don't want my users knowing that I am handing them an interface. If I need to encode either the interface or the implementation, I choose the implementation. Eg: ShapeFactoryImp is even okay.

### Class Names

!!! question
    Classes and objects should have noun or noun phrase names like Customer, WikiPage, Account and AddressParser. Avoid words like Manager, Processor, Data or Info in the name of a class. A class name should not be a verb.

### Method Names
- Method names should have verb or verb phrases like postPayment, deletePage or save.
- Accessors should be named for their value and prefixed with get, set and is, as per javaben standard.
- Pick one word per concept. For example, don't use fetch, retrive and get in different classes. 
- Use solution domain names. Eg: The name 'AccountVisitor' means a great deal to a programmer who is familiar with the Visitor pattern. 
- When there are no solution domain names, use the next best option of going with a name from the problem domain. 

## Functions
- Keep functions as small and focused as possible. 
- Ideally lesser than 10 lines. Should not be more than 20 lines - if so, break them down.
- Follow the Single Responsibility Principle.
- Aim for functions to do one thing well.
- We want the code to read like a top-down narrative.

!!! note "Maintaining Level of Abstraction or Depth"
    Function calls next to each other should be at the same level of abstraction or depth. It should not be mix and match of high level function calls and low level function calls of various levels.

## Comments
- Write necessary comments for clarification.
- Avoid redundant comments stating the obvious.

## Formatting
- Maintain consistent code formatting.
- Use indentation, spacing, and line breaks effectively.

## Avoid Duplication
- Refactor to eliminate code duplication.
- Use functions or classes for common logic.

## Function Arguments
- Limit the number of function arguments (ideally, three or fewer).
- Avoid flags or boolean parameters.

## Error Handling
- Use exceptions for exceptional cases.
- Provide informative and actionable error messages.

## Testing
- Write comprehensive tests for code validation.
- Follow the Arrange-Act-Assert (AAA) pattern.

## Class Design
- Keep classes small and focused.
- Follow the Single Responsibility Principle.
- Aim for cohesion within a class.

## Readability
- Write code as if for beginners.
- Prioritize readability over cleverness.

## Dependency Management
- Minimize dependencies between modules and classes.
- Favor Dependency Inversion Principle.

## Continuous Refactoring
- Regularly revisit and improve code.
- Don't postpone refactoring; it's an ongoing process.