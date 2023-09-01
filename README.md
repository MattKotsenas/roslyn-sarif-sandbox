Spike repo for working with Roslyn and SARIF logs

# Building Roslyn

```powershell
git submodule update --init --recursive

pushd ./roslyn
.\Restore.cmd
.\build -Configuration Release -Pack
popd
```

# Updating NuGet reference

Pulling in a new version of the Roslyn submodule may (or may not) bump the NuGet versions of the packages. In either
case we have work to do, as either NuGet will cache the old version (and not pick up our updates) or reference a stale
package. To fix:

```powershell
dotnet nuget locals all --clear
dotnet add package Microsoft.Net.Compilers.Toolset --prerelease
```

# Running tool

```powershell
dotnet build
```