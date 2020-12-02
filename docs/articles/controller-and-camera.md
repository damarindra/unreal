When we start Unreal Engine, we thought Camera and Controller is quite the same, since when we rotate our Controller *(AddControllerPitchInput, etc)*, camera also rotated. But, it was so wrong!

## **Controller**

The controller is an actor that control our character/pawn. It just represents the rotation, so when we want to add movement input, we usually doing like this

```cpp
const FRotator Rotation = Controller->GetControlRotation();
const FRotator YawRotation(0, Rotation.Yaw, 0);

const FVector Direction = FRotationMatrix(YawRotation).GetUnitAxis(EAxis::Y);

AddMovementInput(Direction, Axis);
```

What Controller doing when we code like this? Camera mimicking the controller, resulting match rotation on some axis between controller and rotation. 

## **Camera**

Camera is controlled by PlayerCameraManager. Usuall,y we don't code it if we just make a simple camera following pawn. Read [*Player Camera Manager.*](https://damarindra.github.io/unreal/articles/player-camera-manager/) Camera can be followed by controller rotation whenever we using *SpringArmComponent* and enable property like `inherit controller rotation`.

## **Conclusion**

Controller is an actor that manage how the control will look, it just a representation of the rotation, so we can get forward, right, up direction from the controller, not player pawn. When a Camera using *SpringArmComponent* and `inherit controller rotation`, you can imagine your controller is a camera, but it was **NOT!** Remember this!