# XASSET 4.0

A more streamlined, efficient and secure Unity Resource Management Solution for you.
- Official Website: <https://www.xasset.org>
- Github: <https://github.com/xasset/xasset>
- QQ Group: [693203087](https://jq.qq.com/?_wv=1027&k=5DyV09a)

[中文请点这里](#中文文档)

## New Features

- **Updater** supports checking individual and merged files updates, merged file is a big file which contains all bunch of resources generated by VFS technology, it requires enable VFS to use, or it will only download individual files fo updates.
- **VFS** supports specific file prefix to read and write, which is a highly efficient resource-encryption solution, and it considerable enhanced IO performance in Android devices.
- **Versions** supports version conrtols for resource files in any prefix, which is easier to control Wwise,Fmod,etc. resources.
- **Downloader** supports resume download from breakpoint, verify fingerprint, restore exceptions (Automatically Redownload if download failed), and modify concurrent number of downloads.
- **SearchPath** a more intelligent search path machinism.
- **Lazy GC** a more efficient resource collect strategy.

## Main Features

- **Runtime Mode**: can be used in Unity Editor without building AssetBundles, which means there is no need to waste time on waiting builds while developing.
- **Does not Depend on Coroutines**: compare to other solutions which highly depends coroutine, XAsset performs better, and developers can use less codes to write nicer and more efficient asynchronous parallel codes.
- **Use reference counts to manage life cycle of object**: Avoid repeated loads and accidentally unload, which can properly handle life cycle of objects. It doesn't use weak reference, which is more convinient to use in multiple coding language environment, eg. avoid C# has to wait for Lua to call GC so it can recycle resource while cross-referencing in C# and Lua.
- **Building strategy base on Rules Setting**: After set the rules, base-code will automatically collect all resources to build, and will analyse the redundancies and confilcts, then optimize automatically. It can effectively solve the redundancy of most non-built-in resources.
- **Non-generic API design**: more friendly to Lua, more convinient to use in multiple coding language environment.

## More About
- ZhiHu Articles: [XASSET 4.0 Publish Notice](https://zhuanlan.zhihu.com/p/158040305)
- ZhiHu Articles: [XASSET 4.0 Quick Start Guide](https://zhuanlan.zhihu.com/p/69410498)

## Test data

| Performence of IO and Constucing in different platform (ms) | VFS     | BUILDIN |
| ----------------------------------------------------------- | ------- | ------- |
| PC (Win10+i7=10700F CPU2.9GHz 64bit 16GB of RAM)            | 310.76  | 354.88  |
| Android (Sony XZs)                                          | 2179.63 | 2740.27 |
| iOS (iPhone 7)                                              | 629.10  | 593.74  |
| MacBook Pro (macOS15.5 2.9GHz 6Core i9 64bit 32GB of RAM)   | 180.29  | 181.90  |

*Note*：Loads about 662 Textures

## Development Environment

- Unity Version: Unity2017.4.34f1 (Now supports 2019)
- Language environment: .net 3.5 (Supports .net4.x and .net core)
- Operarting System: Win 10

## Contributors

- [yusjoel](https://github.com/yusjoel)
- [hemingfei](https://github.com/hemingfei)
- [veboys](https://github.com/veboys)
- [woshihuo12](https://github.com/woshihuo12)
- [CatImmortal](https://github.com/CatImmortal) 
- [ZhangDi](https://github.com/ZhangDi2018)
- [QuinShuai](https://github.com/QuinShuai)
- [songtm](https://github.com/songtm)
- [woodelfLee](https://github.com/woodelfLee)
- [LostEarth](https://github.com/LostEarth)
- [Coeur](https://github.com/Coeur)
- [XINCGer](https://github.com/XINCGer)
- [烟雨迷离半世殇](https://www.lfzxb.top/)
- [土豆](https://www.xasset.org/)
- [JasonXuDeveloper](https://github.com/JasonXuDeveloper)

## More Repository 

- [ET](https://github.com/egametang/ET) Unity3D Client And C# Server Framework
- [Loxodon Framework](https://github.com/cocowolf/loxodon-framework) MVVM Framework for Unity3D(C# & XLua)
- [QFramework](https://github.com/liangxiegame/QFramework) Your first K.I.S.S Unity 3D Framework
- [TinaX Framework](https://tinax.corala.space/) A simple, complete and delightful, ready to use Unity-based framwork
- [LuaProfiler-For-Unity](https://github.com/ElPsyCongree/LuaProfiler-For-Unity) Lua Profiler For Unity, supports XLua、SLua、ToLua
- [JEngine](https://github.com/JasonXuDeveloper/JEngine) A streamlined and easy-to-use framework base on XAsset & ILRuntime which supports hot-update codes and resources in Unity.

<br><br><br><br>


# 中文文档

为你提供更精简、高效、安全的Unity资源管理方案。
- 官网：<https://www.xasset.org>
- Github：<https://github.com/xasset/xasset>
- QQ群：[693203087](https://jq.qq.com/?_wv=1027&k=5DyV09a)

## 新特性

- Updater 支持大小包版本更新检查的程序，大包是把基于VFS技术生成的一种包含了所有资源文件的大文件，需要开启VFS才能使用，不开启或者已经下载过大包之后，只会进行小包更新。
- VFS 自定义格式的文件读写支持，实现了一种非常高效的资源加密方案，并且在测试的Android设备上改方案可以让资源加载的IO性能得到可观的提升。
- Versions 支持任意格式的资源文件的版本管理，可以非常方便的对Wwise、Fmod等自定义格式的文件进行版本控制。
- Downloader 支持断点续传、指纹校验、异常复原（下载失败后自动重新下载）和并发数量配置的资源下载组件。
- SearchPath 更智能的寻址机制。
- Lazy GC 更高效的资源回收策略。

## 主要特点

- 开发模式：编辑器下可以在不用构建AB的环境中使用，平常开发时可以无需为漫长的Build过程耗费大量的时间。
- 对协程无依赖：相对于高度依赖协程的方案，这种设计不但在性能上更有优势，同时，业务层可以用更少的Coding写出更优雅高效的并行异步加载业务。
- 用引用计数管理对象生命周期：避免重复加载与轻易卸载，让资源对象的生命周期得到妥善处理。并且没有使用WeakReference，可以更方便在跨语言环境中使用，例如避免Lua和C#的交叉引用导致C#这边需要等Lua先GC才能回收资源。
- 基于规则配置的打包策略，配置好打包规则后，底层会自动收集所有要打包的资源，并分析其冗余和冲突，再进行自动优化，可以有效的解决大部分非内建的资源的冗余情况。
- 非泛型接口设计: 对Lua更友好，可以更方便的在跨语言的环境中使用。

## 了解更多

- 知乎专栏：[XASSET 4.0发布预告](https://zhuanlan.zhihu.com/p/158040305)
- 知乎专栏：[XASSET 4.0入门指南](https://zhuanlan.zhihu.com/p/69410498)

## 测试数据

| VFS在各个平台的IO+对象构建性能（毫秒）        | VFS     | BUILDIN |
| --------------------------------------------- | ------- | ------- |
| PC（Win10+i7=10700F CPU2.9GHz 64位 16GB内存） | 310.76  | 354.88  |
| Android（Sony XZs）                           | 2179.63 | 2740.27 |
| iOS（iPhone 7）                               | 629.10  | 593.74  |
| MacBook Pro（macOS15.5 2.9GHz 6核 i9 64位 32GB内存） | 180.29  | 181.90  |

*注*：大约读取了 662 张贴图资源

## 开发环境

- 引擎版本：Unity2017.4.34f1（已经支持2019）
- 语言环境：.net 3.5（支持.net4.x以及.net core）
- 操作系统：Win 10

## 贡献成员

- [yusjoel](https://github.com/yusjoel)
- [hemingfei](https://github.com/hemingfei)
- [veboys](https://github.com/veboys)
- [woshihuo12](https://github.com/woshihuo12)
- [CatImmortal](https://github.com/CatImmortal) 
- [ZhangDi](https://github.com/ZhangDi2018)
- [QuinShuai](https://github.com/QuinShuai)
- [songtm](https://github.com/songtm)
- [woodelfLee](https://github.com/woodelfLee)
- [LostEarth](https://github.com/LostEarth)
- [Coeur](https://github.com/Coeur)
- [XINCGer](https://github.com/XINCGer)
- [烟雨迷离半世殇](https://www.lfzxb.top/)
- [土豆](https://www.xasset.org/)
- [JasonXuDeveloper](https://github.com/JasonXuDeveloper)

## 更多项目

- [ET](https://github.com/egametang/ET) Unity3D Client And C# Server Framework
- [Loxodon Framework](https://github.com/cocowolf/loxodon-framework) MVVM Framework for Unity3D(C# & XLua)
- [QFramework](https://github.com/liangxiegame/QFramework) Your first K.I.S.S Unity 3D Framework
- [TinaX Framework](https://tinax.corala.space/) “开箱即用”的Unity独立游戏开发工具
- [LuaProfiler-For-Unity](https://github.com/ElPsyCongree/LuaProfiler-For-Unity) Lua Profiler For Unity支持 XLua、SLua、ToLua
- [JEngine](https://github.com/JasonXuDeveloper/JEngine) 一个基于XAsset&ILRuntime，精简好用的热更框架
