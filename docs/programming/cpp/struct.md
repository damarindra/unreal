Struct in unreal has a special macro to enable usage on the Blueprint version. The macro is `USTRUCT()`. To make it blueprint type, you can pass the BlueprintType inside `USTRUCT(BlueprintType)`.


```cpp
//If you want this to appear in BP, make sure to use this instead
//USTRUCT(BlueprintType)
USTRUCT()
struct FJoyStruct{
	GENERATED_BODY()
	//Always make USTRUCT variables into UPROPERTY()
	//    any non-UPROPERTY() struct vars are not replicated
	// So to simplify your life for later debugging, always use UPROPERTY()
	UPROPERTY()
 	int32 SampleInt32;
	//If you want the property to appear in BP, make sure to use this instead
	//UPROPERTY(BlueprintReadOnly)
	UPROPERTY()
	AActor* TargetActor;
	//Set
	void SetInt(const int32 NewValue)
	{
    		SampleInt32 = NewValue;
	}
	//Get
	AActor* GetActor()
	{
		return TargetActor;
	}
	//Check
	bool ActorIsValid() const
	{
	if(!TargetActor) return false;
	return TargetActor->IsValidLowLevel();
	}
	//Constructor
	FJoyStruct() 	{
		//Always initialize your USTRUCT variables!
		//   exception is if you know the variable type has its own default constructor
		SampleInt32 	= 5;
		TargetActor = NULL;
	}
};
```

```cpp
USTRUCT()
struct FParticleStruct{
  GENERATED_BODY()
  UPROPERTY()
  UParticleSystemComponent* PSCPtr;
  UPROPERTY() 	float LifeTime;
  void SetColor() 	{
  //
  }
  FLinearColor GetCurrentColor() const 	{
  //
  }
  //For GC
  void Destroy() 	{
    PSCPtr = nullptr;
  }
  //Constructor
  FParticleStruct()
  {
    PSCPtr = NULL;
    LifeTime = -1;
  }
};
```