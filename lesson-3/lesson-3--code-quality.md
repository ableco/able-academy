# Code Quality
Able Academy Lesson 3

## Code Quality Principles

#### 1. Organization: How components integrate with each other
#### 2. Readability: How individual components are built
#### 3. Extensibility: Safeguards for development that maintain organization and readability

## Organization

Well-organized code maintains a predictable structure that is self-reinforcing over time.

* Increases clarity and understanding of what the code is doing at a high level
* Focused around interaction between objects
* Larger in scope: application architecture, infrastructure, or code paths
* Clear file structure is just the beginning!

### General Strategies

* Bias towards modularity, but keep it maintainable!
  * Code that is too modular will be impossible to maintain
  * Example: Separation of API and client code has many benefits with limited downside
  * Anti-example: Original MVC concept did not allow models and views to communicate
* Minimize coupling between objects
  * Avoid unmanageable webs of dependency
  * Unidirectional flows do this well
* Consistency and repeatability are key
  * Consistency => predictability => understandability
  * Also allows for interchangeability and code reuse
  * Example: API endpoints using the same method to render responses

### Readability

### Extensibility
