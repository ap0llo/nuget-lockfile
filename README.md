# nuget-lockfile

Repository to demonstrate the usage of NuGet lock files.

In this repository, NuGet lock files are enabled in [ConsoleApplication.csproj](src\ConsoleApplication\ConsoleApplication.`csproj) by setting `RestorePackagesWithLockFile` to `true`:

```xml
  <PropertyGroup>
    ...
    <RestorePackagesWithLockFile>true</RestorePackagesWithLockFile>
    ...
  </PropertyGroup>
```

Additionally, the "locked mode" is enabled:

```xml
  <PropertyGroup>
    ...
    <RestoreLockedMode>true</RestoreLockedMode>
    ...
  </PropertyGroup>
```

This means build/restore will fail, if the lock file does not match the referenced packages.

To update the lock file, run a restore with the locked mode disabled, e.g.:

```
dotnet build .\src\ConsoleApplication\ConsoleApplication.csproj /p:RestoreLockedMode=false
```