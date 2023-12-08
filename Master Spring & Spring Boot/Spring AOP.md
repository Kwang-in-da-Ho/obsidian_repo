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
### 2. Runtime
* Join Point 
	* When pointcut condition is true, the advice is excecuted*
	* A specific execution instance is called Join Point