> Pro tips : Use SSD / m.2. Your CPU can't even handle your slower HDD.

All step can be found in the [official documentation](https://docs.unrealengine.com/en-US/Programming/Development/BuildingUnrealEngine/index.html)


## Adding Plugin from Marketplace

Adding a plugin that you already purchase on the marketplace is quite troublesome. What you need to do is:

1. Download Unreal Engine that same version as your source engine, just select binary only, so you don't waste your drive space
2. Download the plugin
3. Go to UE4/Plugin and copy the Marketplace folder and paste to your UE4Source/Plugin, use symlink if you want automatically update all plugin.
4. Open GenerateProjectFiles.bat to update the project, so the plugin can be included.
5. Compile the engine