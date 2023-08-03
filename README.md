Spike repo for working with Roslyn and SARIF logs

# Building Roslyn

```powershell
git submodule update --init --recursive

pushd ./roslyn
.\Restore.cmd
.\build -Configuration Release -Pack
popd
```

# Running tool

```powershell
dotnet build
```