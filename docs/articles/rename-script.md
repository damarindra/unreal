# How to do it then?

There is 2 Type of renaming, one is really simple, no sweating at all. And the other, you need a lot of step.

## Simple Rename | Basically rename your script and use redirector | Not Recommend

This step is quite simple, the blueprint version of a renamed script is fine. But, the problem is the generated.h is still using the old one.

- Open **DefaultEngine.ini** and under  section add the below line:

    [/Script/Engine.Engine]

```
+ActiveClassRedirects=(OldClassName=”/Script/MyAwesomeClass”,NewClassName=”/Script/MyNewClass”)
```

Source : [https://unrealxeditor.wordpress.com/2015/05/28/tip-renaming-c-classes-without-breaking-your-project/](https://unrealxeditor.wordpress.com/2015/05/28/tip-renaming-c-classes-without-breaking-your-project/)

Typing help : [https://github.com/EpicGames/UnrealEngine/blob/release/Engine/Config/BaseEngine.ini#L240](https://github.com/EpicGames/UnrealEngine/blob/release/Engine/Config/BaseEngine.ini#L240)

## Easier than below, but it actually the same

1. you need to create a new class for the renamed script.
2. Copy all of the script from old one to the new script.
3. Compile and make sure success.
4. Reparent all the blueprint from the old script to the new script
5. Close UE4 and VS
6. Delete the old script.
7. Delete folders . Also delete the

    **vs, Build, Intermediate, and Saved**

    **vs project solution**

    .

8. Right click project file and Generate Visual Studio Project.
9. Rebuild
10. Done!

## Hard but RECOMMEND!

This step is quite complicated. Basically you need a backup, commit and push to git first before doing this action. The idea is, reparent all of the blueprints based on the script that we will rename it. Let’s do it!

1. Reparent all of the blueprints based on the script that we will rename it. Ex: if your script is based on Character, let just call it

```
public class AMyCharacter : ACharacter
```

just reparent the blueprint version to Character, let it be an error, just ignore it for now! **Save All!**

1. Tips : to see all blueprint that inherit from the class, right click the script in Unreal, select Reference Viewer
2. Close Unreal Engine
3. Rename the  and . This basically will slow down your VS.

    class name

    file name

4. Fix the script that depends on our renamed script, for example I rename my script with , then find the error script since we have rename the file. Change it into like this **#include “MyAwesomeCharacter.h”**.

    MyAwesomeCharacter

5. Change the **#include “MyCharactergenerated.h”** to **“MyAwesomeCharacter.generated.h”**
6. Save all changes, close visual studio. If prompt open, just click Save (filter structure changes).
7. Delete folders . Also delete the

    **vs, Build, Intermediate, and Saved**

    **vs project solution**

    .

8. Right click project file and Generate Visual Studio Project.
9. Open the project sln.
10. Rebuild Solution.
11. Ctrl + F5 / Open the project.
12. Your Blueprint file is still fine, not corrupted.
13. Still remember our first step? Reparent the blueprint to the renamed class, and now you’re done!

## **(Haven’t Tried it, but worth to try) Using tools**

Link : [https://samcarey.itch.io/ue4-tools-open-source-tool](https://samcarey.itch.io/ue4-tools-open-source-tool)