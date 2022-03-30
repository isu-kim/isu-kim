# Programming Conventions & Styles
A document for myself for recording my programming styles and conventions.

## C, C++
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
