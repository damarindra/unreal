This just a simple guide about the reference in unreal cpp.


## Passing Class Reference

```cpp
TSubclassOf<class AActorClass> ActorClass;
SomeFunction(ActorClass->GetClass());
```

## Pointer Reference

Basically, any UObject type needs to use a pointer.

### What about reference?

You can passing reference to the parameter, even when the type is pointer such as

![https://damarindra.slite.com/api/files/fv9X30Kuwo/image.png](https://damarindra.slite.com/api/files/fv9X30Kuwo/image.png)

Don't confuse with reference, it is just like a regular variable, but connected to the original variable.