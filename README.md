# .NET for LoongArch64 (non-LSX)

本仓库提供自动构建的 LoongArch64 指令集，无 LSX 向量扩展的 .NET SDK。支持无 LSX 的新世界系统，如 LS2K0300 平台。

当前为实验性支持，请在 [GitHub Actions](https://github.com/driver1998/dotnet-nolsx-build/actions) 下载二进制包。

This repo provides automatic builds of .NET SDK for LoongArch64 with no LSX vectors (march=loongarch64). Supports new-world systems with no LSX support, like LS2K0300 based systems.

Currently expermental, please get the build from [GitHub Actions](https://github.com/driver1998/dotnet-nolsx-build/actions).

# Contents / 内容介绍

## RID linux-loongarch64
该 RID 适用于以 glibc 为 C 运行时库的 LoongArch64 Linux 发行版，也就是大多数发行版。所需的最低 glibc 版本为 **2.41**。

This RID is suitable for use on LoongArch64 Linux distributions with glibc as the C runtime library, which include most distributions out there. A minimum glibc version of 2.41 is needed.

- dotnet-artifacts-linux-loongarch64: \
  .NET 运行时，NativeAOT/Crossgen2 编译器及其它原生库的 NuGet 包。可用于建立交叉编译时需要的本地 NuGet 仓库。 \
  NuGet packages that make up the .NET runtime, NativeAOT/Crossgen2 compiler, and other native libraries. Can be used to build a local NuGet repo for cross-building purposes.
- dotnet-sdk-linux-loongarch64: \
  在 LoongArch 系统上运行的 .NET SDK 本体。\
  .NET SDK itself for running on LoongArch systems.

## RID linux-musl-loongarch64
该 RID 适用于以 musl 为 C 运行时库的 LoongArch64 Linux 发行版，如 Alpine Linux 等。所需的最低 musl 版本为 **1.2.5**。

This RID is suitable for use on LoongArch64 Linux distributions with musl as the C runtime library, such as Alpine Linux. A minimum musl version of **1.2.5** is needed.

- dotnet-artifacts-linux-musl-loongarch64: \
  .NET 运行时，NativeAOT/Crossgen2 编译器及其它原生库的 NuGet 包。可用于建立交叉编译时需要的本地 NuGet 仓库。 \
  NuGet packages that make up the .NET runtime, NativeAOT/Crossgen2 compiler, and other native libraries. Can be used to build a local NuGet repo for cross-building purposes.
  
- dotnet-sdk-linux-musl-loongarch64: \
  在 LoongArch 系统上运行的 .NET SDK 本体。\
  .NET SDK itself for running on LoongArch systems.

### Note

在运行时，还需要一些额外依赖。以 Alpine Linux 的包名列举如下，至少需要这些：

Additional dependencies are needed at runtime. At least the below are needed, in terms of Alpine Linux package names:

- libgcc
- libstdc++
- icu-libs

## Acknowledgements / 鸣谢

- Loongson and Microsoft
- https://github.com/loongson-community/dotnet for a stable LoongArch .NET tree
- https://github.com/dkurt/dotnet_riscv for a minimal build script that fits in GitHub Actions runners
