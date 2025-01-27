# Micro Benchmarks

This folder contains micro benchmarks that test the performance of .NET Runtime(s).

## Tooling

To run the benchmarks, you need to download dotnet cli or use the python script, please see [Prerequisites](../../../docs/prerequisites.md) for more.

We use BenchmarkDotNet as the benchmarking tool, you can read more about it in [our short summary](../../../docs/benchmarkdotnet.md) (it's recommended). The key thing that you need to remember is that **BenchmarkDotNet runs every benchmark in a dedicated process and stops the benchmarking when a specified level of precision is met**.

## Quick Start

The first thing that you need to choose is the Target Framework. Available options are: `netcoreapp2.0|netcoreapp2.1|netcoreapp2.2|netcoreapp3.0|net461`. You can specify the target framework using `-f|--framework` argument. For the sake of simplicity, all examples below use `netcoreapp3.0` as the target framework.

To run the benchmarks in Interactive Mode, where you will be asked which benchmark(s) to run:

```cmd
dotnet run -f netcoreapp3.0
```

To list all available benchmarks ([read more](../../../docs/benchmarkdotnet.md#Listing-the-Benchmarks)):

```cmd
dotnet run -f netcoreapp3.0 --list flat|tree
```

To filter the benchmarks using a glob pattern applied to namespace.typeName.methodName ([read more](../../../docs/benchmarkdotnet.md#Filtering-the-Benchmarks)):

```cmd
dotnet run -f netcoreapp3.0 --filter *Span*
```

To profile the benchmarked code and produce an ETW Trace file ([read more](../../../docs/benchmarkdotnet.md#Profiling)):

```cmd
dotnet run -f netcoreapp3.0 --filter $YourFilter --profiler ETW
```

To run the benchmarks for multiple runtimes ([read more](../../../docs/benchmarkdotnet.md#Multiple-Runtimes)):

```cmd
dotnet run -f netcoreapp2.1 --filter * --runtimes netcoreapp2.1 netcoreapp3.0 corert
```

## Private Runtime Builds

If you contribute to CoreFX/CoreCLR and want to benchmark **local builds of .NET Core** you need to build CoreFX/CoreCLR in Release (including tests) and then provide the path(s) to CoreRun(s). Provided CoreRun(s) will be used to execute every benchmark in a dedicated process:

```cmd
dotnet run -f netcoreapp3.0 --filter $YourFilter --coreRun "C:\Projects\coreclr\bin\tests\Windows_NT.x64.Release\Tests\Core_Root\CoreRun.exe"
```

To make sure that your changes don't introduce any regressions, you can provide paths to CoreRuns with and without your changes and use the Statistical Test feature to detect regressions/improvements ([read more](../../../docs/benchmarkdotnet.md#Regressions)):

```cmd
dotnet run -f netcoreapp3.0 \
    --filter BenchmarksGame* \
    --statisticalTest 3ms \
    --coreRun \
        "C:\Projects\corefx_upstream\bin\runtime\netcoreapp-Windows_NT-Release-x64\CoreRun.exe" \
        "C:\Projects\corefx_fork\bin\runtime\netcoreapp-Windows_NT-Release-x64\CoreRun.exe"
```

If you **prefer to use dotnet cli** instead of CoreRun, you need to pass the path to cli via the `--cli` argument.

BenchmarkDotNet allows you to run the benchmarks for private builds of [Full .NET Framework](../../../docs/benchmarkdotnet.md#Private-CLR-Build) and [CoreRT](../../../docs/benchmarkdotnet.md#Private-CoreRT-Build)

We once again encourage you to read the [full docs about BenchmarkDotNet](../../../docs/benchmarkdotnet.md#table-of-contents).

---

### Categories

Every micro benchmark should belong to either CoreCLR, CoreFX or ThirdParty category. It allows for proper filtering for CI runs:

* CoreCLR - benchmarks belonging to this category are executed for CoreCLR CI jobs
* CoreFX - benchmarks belonging to this category are executed for CoreFX CI jobs
* ThirdParty - benchmarks belonging to this category are not going to be executed as part of our daily CI runs. We are going to run them periodically to make sure we don't regress any of the most popular 3rd party libraries.

Adding given type/method to particular category requires using a `[BenchmarkCategory]` attribute:

```cs
[BenchmarkCategory(Categories.CoreFX)]
public class SomeType
```

### Enabling given benchmark(s) for selected Operating System(s)

This is possible with the `AllowedOperatingSystemsAttribute`. You need to provide a mandatory comment and OS(es) that benchmark(s) can run on.

```cs
[AllowedOperatingSystems("Hangs on non-Windows, dotnet/corefx#18290", OS.Windows)]
public class Perf_PipeTest
```
