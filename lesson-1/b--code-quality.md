# What makes high quality code?

The code we deliver at Able is a critical part of what we do. It is important to align the team on what factors contribute to high quality code. 

### Able strives to deliver code that is: ###

### 1. Organized
### 2. Readable
### 3. Extensible

# 1. Code organization

Well-organized code maintains a predictable structure that is self-reinforcing over time. Examples include:

* Coherent naming conventions that help to inform how to name new objects. 
* An intuitive directory structure that makes it obvious what code belongs where.
* Well-defined responsibilities for each section of the codebase. Redux action, reducers, and state are a good example of code that is not vague or ambiguous in its purpose.

The most direct way code organization can be self-reinforcing is by limiting ambiguity and edge cases. Well-organized code strives to be consistent and predictable. Over time, edge cases introduce breaks in consistency that eventually undermine the code's predictability.


** (Needs more concrete examples) **
 
** Rough notes -- need to refine: ** 
1. Code reviews are an essential tool to ensure organizational structures remain intact.
2. Naming conventions with a consistent pattern are easier to follow when nming new objects. These pattern should be focused and leave little room for deviation. Inconsistent naming or ambiguous conventions reduce focus and detract from established patterns.
3. Rails is an example of disorganized code that does not reinforce any structure. Presentational code can live in views or controllers, business logic can exist in controllers or models, and placement is usually a judgment call determined by the current contributor. Equally unclear are the different roles of Concerns, Services, etc.

# 2. Readable code

Readable code is code that is easily understood. Given a method, class, or system, its readability is measured by how quickly and easily a reader can understand what its purpose is.

The most readable code follows the **single responsibility principle** which states that "a class should only have one reason to change." Each method, class, or system should do one thing, and one thing only.

# 3. Extensibility

Extensibility describes the ease with which new code can be introduced to the existing sytem. Extensibility further builds on the idea of self-reinforcing code.