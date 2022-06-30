# Programming Conventions & Styles
A document for myself for recording my programming styles and conventions. Will be trying to follow this one after June 2022.

## C, C++
This is basically a modified version of `clang-tidy` + `K&R`  style combined. (As well as my own styles.

### File Header Comments
Header comments must be placed before anything in the source code. 
#### File Introduction Comment - For ExampleClass.h
```
//  
// @file : ExampleClass.h  
// @author : Gooday2die (Isu Kim) @ dev.gooday2die@gmail.com  
// @brief : A file that defines all member functions for class ExampleClass
//
```

#### File Introduction Comment - For ExampleClass.cpp
```
//  
// @file : ExampleClass.cpp  
// @author : Gooday2die (Isu Kim) @ dev.gooday2die@gmail.com  
// @brief : A file that implements all member functions for class ExampleClass
//
```

### Preprocessor & Namespaces for Header
#### Includes, Import & Namespaces
Will be using preprocessor and namespaces in header files in following order

1. `ifndef` and `define` first.
2. Pragma expressions
3. Import libraries
4. Include libraries
5. Include written headers
6. Defines
7. Namespaces & Namespace specific
8. Code section
9. `endif`

Rules are:
- Each expression segments will have 1 new lines.
- Avoid using bare `using namespace std;`, instead use `using std::string` for example.
- After preprocessor and namespaces, make two new lines.

#### Example with Code Snippet
```
#ifndef TEST_H
#define TEST_H
#pragma once

#import "libid:F1AA5209-5217-4B82-BA7E-A68198999AFA"

#include <iostream>
#include <string>
#include <foo>

#include "example1.h"
#include "example2.h"

#define HIGH 1
#define LOW 0

using namespace std;  // Avoid using bare namespaces.
using foo::bar1; // Use one expression at a line. Since using multiple is C++ 17 only feature.
using foo::bar2;

// code section

#endif 
```

### Variable Naming
#### Class 
```
class ClassNameInCamelCase
```
#### Normal Variables and Functions
```
int normalVariables
```
#### Argument Variables
```
void testFunction(int argX, int argY);
```
#### Pointers
```
int* pointer;
```
#### Example with Code Snippet
```
class MathCalculator { // Cammel case class name
private:
	int x;
	int y;
	int* z;
public:
	MathCalculator(int argX, int argY) { 
		this->x = argX;
		this->y = argY;
	}
	int addTwoNumbers() { // Member function naming
		return this->x + this->y;
	}
}
```

### Braces & Sections
#### Conditional  Expressions
```
if (1 == 1) {
	printf("Hello World\n");
} else if (1 == 2) {
	printf("Bye World\n");
} else if (1 == 3) {
	printf("Wow World\n");
} else {
	printf("Goodbye World\n");
}
```
- `{` in the same line with conditional expression.
- Whitespace before `{` or `}`
- Evaluation expressions must have **whitespaces**.  Use `1 == 1` instead of `1==1`.
- Next conditional expression stays in the same line as `}`
- Must have a whitespace between conditional expression and evaluation expression. Use `if (1 == 1)` instead of `if(1 == 1)`

#### Try and Catch
```
try {
	someFunction();
} catch (const std::exception& ex) {
	doCatchFunction();
}
```
- Whitespace between `try` and `{`. Use `try {` instead of `try{`
- Use `const std::exception& ex` instead of `std::exception`. (by Clang-Tidy)
- Same rule as **Conditional  Expressions**

### Documentation
#### Classes
```
// Example.h
/**
  * A class that is for blah blah
  */
class Example {
public: // Declare private, public in this way
	int foo(int, int); // Just do declaration, do not define here.
}
```
#### Functions & Member functoins
```
// Example.cpp
/**
  * A member function that does blah blah blah
  * @param a an int that is for blah blah
  * @param b an int that is for blah blah
  * @return an int that represents blah blah
  */
int Example::foo(int a, int b) {
	return a + b;
}
```


## Python
Strictly follow `PEP-8` style.
