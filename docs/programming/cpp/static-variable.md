Static variable in cpp is unique (I have experience on C# before). So, when creating static variable, you can't access it just like that. What you need to do is declaring that static variable into cpp file.

```cpp
// .h
struct FSimpleStruct{
	static FSimpleStruct Instance;
}

// .cpp
FSimpleStruct FSimpleStruct::Instance;

```