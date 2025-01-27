# .NET Performance

| Public Build Status                         | Internal Build Status                           |
| :------------------------------------------ | :---------------------------------------------: |
| [![public_build_icon]][public_build_status] | [![internal_build_icon]][internal_build_status] |

This repo contains benchmarks used for testing the performance of all .NET Runtimes: .NET Core, Full .NET Framework, Mono and CoreRT.

Finding these benchmarks in a separate repository might be surprising. Performance in a given scenario may be impacted by changes in seemingly unrelated components. Using this central repository ensures that measurements are made in comparable ways across all .NET runtimes and repos. This consistency lets engineers make progress and ensures the customer scenarios are protected.

## Documentation

* [Microbenchmarks Guide](./src/benchmarks/micro/README.md) for information on running our microbenchmarks
* [Real-World Scenarios Guide](./src/benchmarks/real-world/JitBench/README.md) for information on running our real-world scenario benchmarks
* [Benchmarking workflow for CoreFX](./docs/benchmarking-workflow-corefx.md) for information on working with CoreFX

## Contributing to Repository

This project has adopted the code of conduct defined by the Contributor Covenant to clarify expected behavior in our community. For more information, see the [.NET Foundation Code of Conduct](https://dotnetfoundation.org/code-of-conduct).

## Build Status

### Micro Benchmarks

#### CoreFX

| Framework | Windows RS4 x64                                                                             | Windows RS4 x86                                                                             | Ubuntu 16.04 x64                                                                            | Ubuntu 16.04 ARM64                                                                              |
| :-------- | :-----------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------: |
| Core 3.0  | [![CoreFX_windows_RS4_x64_netcoreapp3.0_icon]][CoreFX_windows_RS4_x64_netcoreapp3.0_status] | [![CoreFX_windows_RS4_x86_netcoreapp3.0_icon]][CoreFX_windows_RS4_x86_netcoreapp3.0_status] | [![CoreFX_ubuntu_1604_x64_netcoreapp3.0_icon]][CoreFX_ubuntu_1604_x64_netcoreapp3.0_status] | [![CoreFX_ubuntu_1604_arm64_netcoreapp3.0_icon]][CoreFX_ubuntu_1604_arm64_netcoreapp3.0_status] |
| Core 2.2  | [![CoreFX_windows_RS4_x64_netcoreapp2.2_icon]][CoreFX_windows_RS4_x64_netcoreapp2.2_status] |                                                                                             | [![CoreFX_ubuntu_1604_x64_netcoreapp2.2_icon]][CoreFX_ubuntu_1604_x64_netcoreapp2.2_status] | N/A                                                                                             |
| Core 2.1  | [![CoreFX_windows_RS4_x64_netcoreapp2.1_icon]][CoreFX_windows_RS4_x64_netcoreapp2.1_status] |                                                                                             | [![CoreFX_ubuntu_1604_x64_netcoreapp2.1_icon]][CoreFX_ubuntu_1604_x64_netcoreapp2.1_status] | N/A                                                                                             |
| Core 2.0  | [![CoreFX_windows_RS4_x64_netcoreapp2.0_icon]][CoreFX_windows_RS4_x64_netcoreapp2.0_status] |                                                                                             | [![CoreFX_ubuntu_1604_x64_netcoreapp2.0_icon]][CoreFX_ubuntu_1604_x64_netcoreapp2.0_status] | N/A                                                                                             |
| .NET      | [![CoreFX_windows_RS4_x64_net461_icon]][CoreFX_windows_RS4_x64_net461_status]               |                                                                                             | N/A                                                                                         | N/A                                                                                             |


#### CoreCLR

| Framework | Windows RS4 x64                                                                               | Windows RS4 x86                                                                               | Ubuntu 16.04 x64                                                                              | Ubuntu 16.04 ARM64                                                                                |
| :-------- | :-------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------: |
| Core 3.0  | [![CoreCLR_windows_RS4_x64_netcoreapp3.0_icon]][CoreCLR_windows_RS4_x64_netcoreapp3.0_status] | [![CoreCLR_windows_RS4_x86_netcoreapp3.0_icon]][CoreCLR_windows_RS4_x86_netcoreapp3.0_status] | [![CoreCLR_ubuntu_1604_x64_netcoreapp3.0_icon]][CoreCLR_ubuntu_1604_x64_netcoreapp3.0_status] | [![CoreCLR_ubuntu_1604_arm64_netcoreapp3.0_icon]][CoreCLR_ubuntu_1604_arm64_netcoreapp3.0_status] |
| Core 2.2  | [![CoreCLR_windows_RS4_x64_netcoreapp2.2_icon]][CoreCLR_windows_RS4_x64_netcoreapp2.2_status] |                                                                                               | [![CoreCLR_ubuntu_1604_x64_netcoreapp2.2_icon]][CoreCLR_ubuntu_1604_x64_netcoreapp2.2_status] | N/A                                                                                               |
| Core 2.1  | [![CoreCLR_windows_RS4_x64_netcoreapp2.1_icon]][CoreCLR_windows_RS4_x64_netcoreapp2.1_status] |                                                                                               | [![CoreCLR_ubuntu_1604_x64_netcoreapp2.1_icon]][CoreCLR_ubuntu_1604_x64_netcoreapp2.1_status] | N/A                                                                                               |
| Core 2.0  | [![CoreCLR_windows_RS4_x64_netcoreapp2.0_icon]][CoreCLR_windows_RS4_x64_netcoreapp2.0_status] |                                                                                               | [![CoreCLR_ubuntu_1604_x64_netcoreapp2.0_icon]][CoreCLR_ubuntu_1604_x64_netcoreapp2.0_status] | N/A                                                                                               |
| .NET      | [![CoreCLR_windows_RS4_x64_net461_icon]][CoreCLR_windows_RS4_x64_net461_status]               |                                                                                               | N/A                                                                                           | N/A                                                                                               |

[//]: # (These are the repo links)

[public_build_icon]:                               https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master
[public_build_status]:                             https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master
[internal_build_icon]:                             https://dev.azure.com/dnceng/internal/_apis/build/status/dotnet/performance/dotnet-performance?branchName=master
[internal_build_status]:                           https://dev.azure.com/dnceng/internal/_build/latest?definitionId=306&branchName=master

### Real World Benchmarks

#### ML.NET

| Framework | Windows RS4 x64                                                                                 | Ubuntu 16.04 x64                                                                                |
| :-------- | :---------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------: |
| Core 3.0  | [![mldotnet_windows_RS4_x64_netcoreapp3.0_icon]][mldotnet_windows_RS4_x64_netcoreapp3.0_status] | [![mldotnet_ubuntu_1604_x64_netcoreapp3.0_icon]][mldotnet_ubuntu_1604_x64_netcoreapp3.0_status] |

[//]: # (These are the CoreFX links)

[//]: # (These are the windows x64 links)
[CoreFX_windows_RS4_x64_netcoreapp3.0_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_netcoreapp3.0
[CoreFX_windows_RS4_x64_netcoreapp3.0_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_netcoreapp3.0
[CoreFX_windows_RS4_x64_netcoreapp2.2_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_netcoreapp2.2
[CoreFX_windows_RS4_x64_netcoreapp2.2_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_netcoreapp2.2
[CoreFX_windows_RS4_x64_netcoreapp2.1_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_netcoreapp2.1
[CoreFX_windows_RS4_x64_netcoreapp2.1_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_netcoreapp2.1
[CoreFX_windows_RS4_x64_netcoreapp2.0_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_netcoreapp2.0
[CoreFX_windows_RS4_x64_netcoreapp2.0_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_netcoreapp2.0
[CoreFX_windows_RS4_x64_net461_status]:            https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_net461
[CoreFX_windows_RS4_x64_net461_icon]:              https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreFX_net461

[//]: # (These are the windows x86 links)
[CoreFX_windows_RS4_x86_netcoreapp3.0_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x86%20micro&configuration=CoreFX_netcoreapp3.0
[CoreFX_windows_RS4_x86_netcoreapp3.0_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x86%20micro&configuration=CoreFX_netcoreapp3.0

[//]: # (These are the ubuntu x64 links)
[CoreFX_ubuntu_1604_x64_netcoreapp3.0_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreFX_netcoreapp3.0
[CoreFX_ubuntu_1604_x64_netcoreapp3.0_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreFX_netcoreapp3.0
[CoreFX_ubuntu_1604_x64_netcoreapp2.2_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreFX_netcoreapp2.2
[CoreFX_ubuntu_1604_x64_netcoreapp2.2_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreFX_netcoreapp2.2
[CoreFX_ubuntu_1604_x64_netcoreapp2.1_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreFX_netcoreapp2.1
[CoreFX_ubuntu_1604_x64_netcoreapp2.1_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreFX_netcoreapp2.1
[CoreFX_ubuntu_1604_x64_netcoreapp2.0_status]:     https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreFX_netcoreapp2.0
[CoreFX_ubuntu_1604_x64_netcoreapp2.0_icon]:       https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreFX_netcoreapp2.0

[//]: # (These are the ubuntu arm64 links)
[CoreFX_ubuntu_1604_arm64_netcoreapp3.0_status]:   https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20arm64%20micro&configuration=CoreFX_netcoreapp3.0
[CoreFX_ubuntu_1604_arm64_netcoreapp3.0_icon]:     https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20arm64%20micro&configuration=CoreFX_netcoreapp3.0

[//]: # (These are the CoreCLR links)

[//]: # (These are the windows x64 links)
[CoreCLR_windows_RS4_x64_netcoreapp3.0_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_netcoreapp3.0
[CoreCLR_windows_RS4_x64_netcoreapp3.0_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_netcoreapp3.0
[CoreCLR_windows_RS4_x64_netcoreapp2.2_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_netcoreapp2.2
[CoreCLR_windows_RS4_x64_netcoreapp2.2_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_netcoreapp2.2
[CoreCLR_windows_RS4_x64_netcoreapp2.1_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_netcoreapp2.1
[CoreCLR_windows_RS4_x64_netcoreapp2.1_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_netcoreapp2.1
[CoreCLR_windows_RS4_x64_netcoreapp2.0_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_netcoreapp2.0
[CoreCLR_windows_RS4_x64_netcoreapp2.0_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_netcoreapp2.0
[CoreCLR_windows_RS4_x64_net461_status]:           https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_net461
[CoreCLR_windows_RS4_x64_net461_icon]:             https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20micro&configuration=CoreCLR_net461

[//]: # (These are the windows x86 links)
[CoreCLR_windows_RS4_x86_netcoreapp3.0_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x86%20micro&configuration=CoreCLR_netcoreapp3.0
[CoreCLR_windows_RS4_x86_netcoreapp3.0_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x86%20micro&configuration=CoreCLR_netcoreapp3.0

[//]: # (These are the ubuntu x64 links)
[CoreCLR_ubuntu_1604_x64_netcoreapp3.0_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreCLR_netcoreapp3.0
[CoreCLR_ubuntu_1604_x64_netcoreapp3.0_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreCLR_netcoreapp3.0
[CoreCLR_ubuntu_1604_x64_netcoreapp2.2_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreCLR_netcoreapp2.2
[CoreCLR_ubuntu_1604_x64_netcoreapp2.2_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreCLR_netcoreapp2.2
[CoreCLR_ubuntu_1604_x64_netcoreapp2.1_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreCLR_netcoreapp2.1
[CoreCLR_ubuntu_1604_x64_netcoreapp2.1_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreCLR_netcoreapp2.1
[CoreCLR_ubuntu_1604_x64_netcoreapp2.0_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreCLR_netcoreapp2.0
[CoreCLR_ubuntu_1604_x64_netcoreapp2.0_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20micro&configuration=CoreCLR_netcoreapp2.0

[//]: # (These are the ubuntu arm64 links)
[CoreCLR_ubuntu_1604_arm64_netcoreapp3.0_status]:  https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20arm64%20micro&configuration=CoreCLR_netcoreapp3.0
[CoreCLR_ubuntu_1604_arm64_netcoreapp3.0_icon]:    https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20arm64%20micro&configuration=CoreCLR_netcoreapp3.0

[//]: # (These are the ML.NET links)

[//]: # (These are the windows x64 links)
[mldotnet_windows_RS4_x64_netcoreapp3.0_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=windows%20RS4%20x64%20mlnet&configuration=mldotnet_netcoreapp3.0
[mldotnet_windows_RS4_x64_netcoreapp3.0_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=windows%20RS4%20x64%20mlnet&configuration=mldotnet_netcoreapp3.0

[//]: # (These are the ubuntu x64 links)
[mldotnet_ubuntu_1604_x64_netcoreapp3.0_status]:    https://dev.azure.com/dnceng/public/_build/latest?definitionId=271&branchName=master&jobName=ubuntu%201604%20x64%20mlnet&configuration=mldotnet_netcoreapp3.0
[mldotnet_ubuntu_1604_x64_netcoreapp3.0_icon]:      https://dev.azure.com/dnceng/public/_apis/build/status/dotnet/performance/performance-ci?branchName=master&jobName=ubuntu%201604%20x64%20mlnet&configuration=mldotnet_netcoreapp3.0
