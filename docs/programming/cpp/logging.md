https://ue4community.wiki/logging-lgpidy6i

Logging an FString

```
UE_LOG(LogTemp, Warning, TEXT("%s"), *YourActor->GetName());
```

Logging a Bool

```
UE_LOG(LogTemp, Warning, TEXT("%s"), ( bYourBool ? TEXT("true") : TEXT("false") ));
```

Logging an Integer

```
UE_LOG(LogTemp, Warning, TEXT("%d"), YourInteger);
```

Logging a Float

```
UE_LOG(LogTemp, Warning, TEXT("%f"), YourFloat);
```

Logging an FVector

```
UE_LOG(LogTemp, Warning, TEXT("%s"), *YourVector.ToString());
```

Logging an Enum

```
UE_LOG(LogTemp, Warning, TEXT("%s"), *StaticEnum<ECollisionChannel>()->GetValueAsString(OutHit.Component->GetCollisionObjectType()));
```