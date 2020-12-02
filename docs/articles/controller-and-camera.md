When we start Unreal Engine, we thought Camera and Controller is quite the same, since when we rotate our Controller *(AddControllerPitchInput, etc)*, camera also rotated. But, it was so wrong!

## **Controller**

The controller is an actor that control our character/pawn. It just represents the rotation, so when we want to add movement input, we usually doing like this

```cpp
const FRotator Rotation = Controller->GetControlRotation();
const FRotator YawRotation(0, Rotation.Yaw, 0);

const FVector Direction = FRotationMatrix(YawRotation).GetUnitAxis(EAxis::Y);

AddMovementInput(Direction, Axis);
```

## **Camera**

Camera is controlled by PlayerCameraManager. Usually we don't code it if we just make simple camera following pawn. Read *Player Camera Manager.* Camera can followed controller rotation whenever we using *SpringArmComponent* and enable inherit controller rotation.

## **Conclusion**

Controller is an actor that manage how the control will look at, it just representation of the rotation, so we can get forward, right, up direction from controller, not player pawn.

Camera is just mimicking the controller rotation, and with help of *SpringArmComponent*, it can inherited from the controller rotation.