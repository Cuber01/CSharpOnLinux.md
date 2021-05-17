# How to use C# tools on Linux

Original: https://github.com/egordorichev/BurningKnight/blob/dev/CompileNetFrameworkOnLinux.md

My setup: Ubuntu 20.4 LTS, mono 6.12.0.122, .NET Core SDK (3.1.408), msbuild 16.6.0, JetBrains Rider as IDE

## Mono

Mono can be used instead of NET Framework 4.x, since there's no NET Framework for Linux

Install mono-devel (you may need to add mono repositories, to do this follow [these instructions](https://www.mono-project.com/download/stable/#download-lin))

```sh
sudo apt-get install mono-devel
```

If your IDE shows tons of errors and/or can't compile the code (but you can compile it in the terminal), you will need:

```sh
sudo apt-get install mono-dbg
```

This is a debugger for mono

## .NET Core SDK 3.1

.NET Core is a successor to .NET Framework. Ironically, it's also a Framework.
Follow these [instructions](https://docs.microsoft.com/en-us/dotnet/core/install/linux) to download the .NET Core

## msbuild

To download msbuild, run:

```sh
sudo apt-get install msbuild
```

## nuget

You don't need nuget to compile the code, it's a package manager for .NET. It can be pretty useful though.

```sh
sudo apt-get install nuget
```

## Monogame templates for Rider

```sh
dotnet new -i MonoGame.Templates.CSharp
```

## Compiling [Burning Knight](https://github.com/egordorichev/BurningKnight)

```sh
# clone the repo
git clone https://github.com/egordorichev/BurningKnight
cd BurningKnight
# install the packages
nuget restore
# build the project
msbuild
# run the game
cd Desktop/bin/Debug/
mono Desktop.exe
```

