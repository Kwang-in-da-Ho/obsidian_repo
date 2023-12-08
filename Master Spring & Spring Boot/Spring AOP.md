# I. What is AOP?
* Used to implement Cross-Cutting Concerns
	* Logging
	* Security
	* Etc...

## II. Important Terminology
### 1. Compile Time
* Advice : what Cross-Cutting Concern code to execute? 
* Pointcut : Expression that identifies which method calls should be intercepted
* Aspect : combination of Advice & Pointcut
* Weaver : the framework that implements AOP
### 2. Runtime
* Join Point 
	* When pointcut condition is true, the Advice is excecuted*
	* A specific execution of an Advice instance is called Join Point

## III. Core Annotations
* `@Before` : before method is executed
* `@After` : called after method execution ***even when an exception is thrown***
* `@AfterReturning` : only after return
* `@AfterThrowing` : only after exception is thrown
* `@Around` : before and after method execution