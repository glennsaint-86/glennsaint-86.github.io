---
layout: single
title:  ".NET 6.0 Missing Project Templates"
date:   2022-04-07 03:00:00 +0800
categories: blog
toc: true
toc_sticky: true
tags: net60 dotnet-cli dotnet-new
#permalink:
published: true
---
It's been ahile that I've touched C# and .NET, the last time I've work was still on .NET Core 3.1. I've decided, to do playaround with **net60** and serve as a refresher for me. My current development playground setup is to use VS Code Dev Containers, so I've decided to create to two Dev containers one for .NET Core 3.1 and .NET 6.0. In this way I can do a side by side comparision. 

# Enumerating and comparing Project Templates
I've run `dotnet new --list` for each dev container to list down the available project templates. In .NET 6.0, the following project templates are not present that are in .NET Core 3.1: 
* WPF Application  *wpf*
* WPF Class Library *wpflib*
* WPF Custom Control Library *wpfcustomcontrollib*
* WPF User Control Library *wpfusecontrollib*
* Windows Forms (WinForms) *Application *winforms*
* Windows Forms (WinForms) Class Library 
* ASP.NET Core wit React.js and Redux *reactredux*

In .NET 6.0 a new project template named `EditorConfig file`  editor config is added. While in .NET Core 3.1 the project template **Unit Test Project** is now renamed as **MSTest Test Project** in .NET 6.0

# Updating Project Templates
At times Microsoft updates there project templates, to get the latest update template,  run the .NET CLI command `dotnet new --update-check`. This will list down the templates that has updates. 

To update simply run `dotnet new --update-apply` to update and install the changes.

# What's next? 
With NET 6.0 they've introduce so called *top level statements* and *minimal APIs*, on my next post I'll compare the *console* project template between .NET Core 3.1 and .NET 6.0 and dig-in into top level statements.