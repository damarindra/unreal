Unreal has some type for handling string. The tl:dr; version is

- **TEXT()** is your friend! Use this to create any type of string.
- **FName** is cheaper, but case-insensitive. It is immutable (can't be manipulated)
- **FText** is for user. Everything that users see, better using `FText`. FText support localization, that's means you can formatting this text, localized text, and so on.
- **FString** is expensive. This like pure string in the other language.

If you want complete guide on string handling, you can read [official documentation](https://docs.unrealengine.com/en-US/Programming/UnrealArchitecture/StringHandling/index.html).