---
layout: single
title:  "Removing bin and obj folder in .NET"
date:   2022-04-17 00:15:00 +0800
categories: blog
toc: true
toc_sticky: true
tags: dotnet dotnet-cli gotcha tech-discoveries
#permalink:
published: true
---
Building .NET applications through `dotnet build` produces the bin and obj folder. While running `dotnet clean` would only delete the files of **bin** folder only. In order to delete these folder when running `dotnet clean`, modify the project file and insert the code below  
```xml
<Target Name="SpicNSpan" AfterTargets="Clean">
    <RemoveDir Directories="$(BaseOutputPath)" />
    <RemoveDir Directories="$(BaseIntermediateOutputPath)" /> 
</Target>
```
Once inserted, run `dotnet clean` these will automatically removed the **bin** and **obj** folder. Below shows illustrations before and after adding the configuration in the project file.

**Before** 
![dotnet-clean-before](/assets/images/dotnet-clean-01.gif)
Running `dotnet clean` doesn't delete the bin and obj folders.

**After**
![dotnet-clean-after](/assets/images/dotnet-clean-02.gif)
Running `dotnet clean` deletes the bin and obj folders. 

## Conclusion
In larger solutions that has multiple projects and some of the projects might reference to other projects, in some cases it needs to remove the obj folder in order to ensure that when `dotnet build` will capture all the code changes. However, most of the time MSBUILD take cares of it without requiring to delete these folders. 
