# __fluffyspoon.template__

[![Build status](https://img.shields.io/azure-devops/build/christopherdemicoli/8c7d1a1e-f368-46cf-bad7-1f2ed587335d/16)](https://img.shields.io/azure-devops/build/christopherdemicoli/8c7d1a1e-f368-46cf-bad7-1f2ed587335d/16) 
[![NuGet](https://img.shields.io/nuget/v/demofluffyspoon.contracts.svg)](https://nuget.org/packages/demofluffyspoon.contracts)

For more information about `dotnet new` templates see [here](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/).

## __Installation__

Use the NuGet package identifier to install a template package.
```sh
dotnet new -i fluffyspoon.template
```

Once installed, all available templates, including the fluffyspoon ones will be listed:
```sh
Templates                                      Short Name               Language          Tags
-----------------------------------------------------------------------------------------------------------
Console Application                            console                  [C#], F#, VB      Common/Console
Class library                                  classlib                 [C#], F#, VB      Common/Library
WPF Application                                wpf                      [C#], VB          Common/WPF
WPF Class library                              wpflib                   [C#], VB          Common/WPF
WPF Custom Control Library                     wpfcustomcontrollib      [C#], VB          Common/WPF
WPF User Control Library                       wpfusercontrollib        [C#], VB          Common/WPF
Windows Forms (WinForms) Application           winforms                 [C#], VB          Common/WinForms
Windows Forms (WinForms) Class library         winformslib              [C#], VB          Common/WinForms
Worker Service                                 worker                   [C#]              Common/Worker/Web
FluffySpoon Orleans Silo                       fs-silo                  [C#]              Solution/Project/Orleans/Silo
Unit Test Project                              mstest                   [C#], F#, VB      Test/MSTest
```

To apply an update to previously installed templates, use this command:
```sh
dotnet new --update-apply
```

If you need to set back your dotnet new list to "factory defaults", use this command:
```sh
dotnet new --debug:reinit
```

## __Usage__

To create a solution using the template, use this command:

```sh
dotnet new fs-silo -n fluffyspoon.email --short-name email
```