# CPU 篇

## 应避免的 CPU

### AMD 处理器
虽然 AMD CPU 可以运行 Hackintosh，但由于其缺乏原生支持，我们仍建议避免使用。配置过程需要大量额外工作，AMD 用户可参考 [AMD 原生指南](https://vanilla.amd-osx.com)。

常见 AMD 兼容性问题：
- **Adobe 软件兼容性差**
  - Lightroom 目前无解
  - 部分临时方案可禁用功能（非真正修复）：[Adobe 修复指南](https://gist.github.com/naveenkrdy/26760ac5135deed6d0bb8902f6ceb6bd)
- **音频软件崩溃**
  - Cubase 无解，REAPER 需使用 Clang 编译版本
  - Waves 插件易引发崩溃
- **虚拟化支持缺失**
  - Parallels 15（基于 AppleHV）无法运行，VirtualBox 正常
- **Docker 功能受限**
  - Docker Toolbox 依赖 VirtualBox，功能不完整
- **Xcode 模拟器问题**
  - Apple Watch 模拟器在 Catalina 中损坏（Mojave 正常）
- **音频输入需 VoodooHDA**
  - AppleALC 无法驱动麦克风，音质与稳定性下降
- **Ryzen APU 音频漂移**
  - 唯一解决方案：更换 CPU 或使用 USB 声卡
- **睡眠功能难以配置**
  - 部分系统完全无法实现
- **无 CPU 电源管理**
- **USB 端口未全部启用**
  - 需手动在 DSDT 中分配
- **更新延迟**
- ~~第三代 Threadripper 不支持原生安装~~
  - 新版 BIOS 和 OpenCore 已支持 TRx40 芯片组

**不推荐的 AMD CPU 系列**：
- Ryzen 1000/2000/3000 系列
- Athlon 系列
- ThreadRipper 系列
- FX 系列

### Intel 处理器
Intel CPU 可通过仿冒为支持型号实现兼容，但需注意：
- **低端型号（Atom/Celeron/Pentium）的核显无法驱动**
  - 无法实现低成本核显方案
- **X99/LGA 2011-V3 平台问题**
  - 无真实 Mac 采用此架构，macOS 兼容性差

**双路用户注意**：
- macOS 内核最多支持 **64 线程**
- Catalina 系统需使用 [AppleMCEReporterDisabler](https://github.com/acidanthera/bugtracker/files/3703498/AppleMCEReporterDisabler.kext.zip)

**应避免的 Intel CPU/平台**：
- Atom 系列
- Celeron 系列
- Pentium 系列
- X79/LGA 2011
- X99/LGA 2011-V3
- X299/LGA-2066

::: tip 推荐方案
**优先选择现代消费级 Intel CPU**：
- Ivy Bridge 至 Comet Lake 系列在 macOS 中支持完善
:::

## 完全不支持的 CPU

### 老旧 CPU（指令集缺失）
**SSE4.2 缺失**：无法运行 Mojave 及以上系统（可通过修改系统文件绕过，但稳定性差）  
参考 [trashOS 项目](https://github.com/khronokernel/trashOS)  
- Wolfdale（Core2 Duo 系列）
  - E7xxx / E8xxx
- Yorkfield（Core2 Quad 系列）
  - E8xxx / E9xxx

**SSE4.1 缺失**：最高仅支持 OS X 10.11 El Capitan

### 新锐 CPU（补丁未跟进）
尚未有社区补丁支持的最新架构处理器（如 Intel 12 代 Alder Lake 及更新型号）
