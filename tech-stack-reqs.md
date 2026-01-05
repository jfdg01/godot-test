# Setup

## Installations

1. MS .NET 9: `winget install Microsoft.DotNet.SDK.9` in PowerShell
2. Custom EsotericSoftware version of Godot (that includes AnimationPlayer) [esoteric software page](https://esotericsoftware.com/spine-godot#spine-godot-engine-module-downloads):
    * Godot 4.5.1 with C# support (install the correct OS)
    * Export templates for Windows, Linux, macOS: [godot export templates](https://spine-godot.s3.eu-central-1.amazonaws.com/4.2/4.5.1-stable/spine-godot-templates-4.2-4.5.1-stable-mono.tpz)
3. VSCode extensions:
    * nromanov.dotrush
    * muhammad-sammy.csharp
    * godot (geequlimgodot-tools, Godot tools, but for some reason when you search the identifier in the marketplace it doesn't show up)
    * godot (neikeq.godot-csharp-vscode, C# tools for Godot)
    * godot (Godot Files)

## Connect to antigravity (or any other external editor)

1. In Godot: Editor > Editor Settings.
2. Go to Dotnet > Editor > External Editor and select Visual Studio Code / VSCodium
3. Go to Text Editor > External: 
    * Check Use External Editor.
    * Exec Path: Point this to your Antigravity .exe (or binary).
    * Exec Flags: {project} --goto {file}:{line}:{col}.

## Project creation requiremts

Use `compatibility` renderer.

### Project setup
 
In your project root folder, create a new folder named `godot-nuget`:

* Locate the folder where you downloaded the Spine-Godot Editor. Inside, there is a folder: GodotSharp/Tools. Copy all .nupkg and .snupkg files from that Tools folder into your project's new godot-nuget folder

Create a `nuget.config` file with the following content:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <config>
    <add key="repositoryPath" value="./godot-nuget" />
  </config>
</configuration>
```

> These are both provided in this repo.


