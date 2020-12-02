UProperty and UFunction is macro to make any property or function can interact with Blueprint. You can read all the [metadata at here](https://docs.unrealengine.com/en-US/Programming/UnrealArchitecture/Reference/Metadata/index.html) 

# UPROPERTY

## Not Meta

`UPROPERTY(YourOptionHere)`

| Parameter       |                           Details |
| :-------------- | --------------------------------: |
| AdvancedDisplay | Show on bottom hide details panel |


## Meta

`UPROPERY(meta = (YourOptionHere = "Value", AllowPrivateAccess))`

| Parameter                            |                                                                 Details |
| :----------------------------------- | ----------------------------------------------------------------------: |
| UIMin='0.0', UIMax='1.0              |                         Property clamped 0 to 1 and changed into slider |
| AllowPrivateAccess                   |             Allow private / protected modifier to access into Blueprint |
| editcondition="someBoolVariableHere" | disable enable this property. You can use condition like `floatVal > 1` |
