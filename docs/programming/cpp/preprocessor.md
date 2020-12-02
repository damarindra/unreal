Preprocessor is useful in some parts, especially specify code that running on the specific platform.

## WITH_EDITORONLY_DATA

Used for property / variable that you want to use in Editor only.

## WITH_EDITOR

Used for any code that run / read on Editor only, including function definition

```cpp
#if WITH_EDITORONLY_DATA
	bool isDebugMode = false;
#endif

#if WITH_EDITOR
	UFUNCTION(Exec)
	void EnableDebugMode(bool Enable = false);
#endif
```