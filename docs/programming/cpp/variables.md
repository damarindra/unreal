# Common Usage

- Setter Getter is highly recommended. Keep your variable in private / protected is good.
- When you want to use your variable in the blueprint, use **protected** and UPROPERTY BlueprintReadWrite / Something else.
- If you want to use the variable outside of the child class, use **public** / setter getter. **NOTE :** **if you use set get, dont use blueprintReadWrite at the target variable!** Ex:

```cpp
protected:
  float MoveInput;
public:
  UFUNCTION(BlueprintCallable)
  FORCEINLINE float GetMoveInput() const {return MoveInput;}
```

- Why? You will have, if you have BlueprintRead, inside the Blueprint, when you call GetMoveInput, it will reproduce 2 type of getter. And that was not good for future development. Just make it simple!

## Int

C++ care about memory, don't overdue int usage, just use it as you need with proper size

- uint = unsigned int = no negative value
- int = signed int = allow negative value
- uint8 = 0 — 255
- int8 = -128 — 127
- uint16 = 0 — 65535
- int16 = -32768 — 32767
- uint32 = 0 — -4294967295
- int32 = -2147483648 — 2147483647

## Size of c-type data

Source : [https://www.geeksforgeeks.org/c-data-types/](https://www.geeksforgeeks.org/c-data-types/)

| data type              | size(in bytes) |                           range |
| :--------------------- | :------------: | ------------------------------: |
| SHORT INT              |       2        |               -32,768 to 32,767 |
| UNSIGNED SHORT INT     |       2        |                     0 to 65,535 |
| UNSIGNED INT           |       4        |              0 TO 4,294,967,295 |
| INT                    |       4        | -2,147,483,648 TO 2,147,483,647 |
| LONG INT               |       8        | -2,147,483,648 TO 2,147,483,647 |
| UNSIGNED LONG INT      |       8        |              0 TO 4,294,967,295 |
| LONG LONG INT          |       8        |             -(2^63) TO (2^63)-1 |
| UNSIGNED LONG LONG INT |       8        | 0 TO 18,446,744,073,709,551,615 |
| SIGNED CHAR            |       1        |                     -128 TO 127 |
| UNSIGNED CHAR          |       1        |                        0 TO 255 |
| FLOAT                  |       4        |                                 |
| DOUBLE                 |       8        |                                 |
| LONG DOUBLE            |       12       |                                 |
| WCHAR_T                |     2 OR 4     |                1 WIDE CHARACTER |