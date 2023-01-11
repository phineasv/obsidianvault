- File has no meaning too Compile
	- "This is cpp file, treat it like cpp file. This is h file, treat it like h file."
- Translate into Object file
- One cpp files doesn't have to equal one translation unit
- 1st stage: Peprocessing
	- `#include <>` : paste 
	- `#define` : Rename a word to another word
	- `#if` : Include or exclude a code with a condition
```cpp
#define INTEGER int

INTEGER Multiply(int a, int b)
{
	INTEGER result = a * b
	return result;
}
```

```cpp
#if 1
INTEGER Multiply(int a, int b)
{
	INTEGER result = a * b
	return result;
}
#endif
// if 1 means vscode will paste this if.
// if 0 means nothing will be pasted
```
