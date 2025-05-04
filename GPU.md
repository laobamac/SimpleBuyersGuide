# GPU 篇

~~推荐购买 RTX 显卡，我想看看用户在高山狮系统中逐渐意识到根本不支持的痛苦。让 Nvidia 粉丝在缓慢而痛苦的死亡中醒悟，永远不要背叛我们的救世主蒂姆·库克~~  
若想省心，请避开所有非 Kepler 架构的 Nvidia 显卡。当前（很可能永久）图灵（Turing）和伏打（Volta）架构显卡在 macOS 中完全无支持，帕斯卡（Pascal）和麦克斯韦（Maxwell）架构仅支持到 High Sierra 且依赖 Web 驱动（非原生支持，增加系统不稳定性）。

> 但...驱动有了吗？

![Web Drivers](WebDrivers.gif)

**推荐显卡**请参考：[GPU 选购指南](https://dortania.github.io/GPU-Buyers-Guide/)  
**不支持的显卡**也别灰心！通过我们的专利技术：[**如何在 macOS 中屏蔽不支持的 GPU**](https://dortania.github.io/Getting-Started-With-ACPI/Desktops/desktop-disable.html)，小白也能畅享 Mojave 及以上系统！

> 选购显卡时需要避开哪些品牌？

问得好！多数品牌兼容性尚可，但以下品牌需谨慎（可能导致黑屏/系统不稳定）：
- **XFX**（需关闭 CSM/传统模式，强制 UEFI 启动）
- **PowerColor**
- **MSI**（仅 Navi 架构有问题，Vega/Polaris 正常）

注：AMD Navi 显卡支持仍不稳定（WhateverGreen 未完全适配）

::: tip 推荐方案
**优先选择以下 AMD 显卡**：
- Polaris 10/20（RX 4XX/5XX 系列）
- Vega 10/20（RX Vega 56/64/VII）
- Navi 10（RX 5XXX 系列）

**推荐品牌**：
- 蓝宝石（Sapphire）
- 华硕（Asus）
- 技嘉（Gigabyte）
:::

## 完全不支持的 GPU

### Ampere 架构
- RTX 3090/3080/3070  
- Titan RTX  
- RTX 2080 Ti/2080 Super/2080/2070 Super/2070/2060 Super/2060  
- GTX 1660 Ti/1660/1650  
- Quadro RTX 8000/6000/5000/4000  

### Volta 架构
- Titan V/Titan V CEO Edition  
- Quadro GV100  

### Lexa 架构
- RX 540/X  
- RX 550/X  

## 应避免的 GPU

### Pascal 架构
- GTX Titan X（GP 102-400 核心）  
- GTX Titan Xp（GP 102-450 核心）  
- GTX 1080 Ti/1080/1070 Ti/1070/1060/1050 Ti/1050/1030  
- Quadro P400/P600/P620/P1000/P2000/P4000/P5000/P6000/GP100  

### Maxwell 架构
- GTX Titan X（GM 200 核心）  
- GTX 980 Ti/980/970/960/950/750 Ti/745  
- Quadro K620/K1200/K220/M2000/M4000/M5000/M6000  

---

### 技术说明：
1. **术语保留**：
   - 架构名称（Kepler/Pascal/Maxwell）保留英文，中文社区通用
   - 工具名（WhateverGreen）不翻译，避免混淆

2. **兼容性分级**：
   - **完全不支持**：无驱动方案
   - **应避免**：需复杂补丁或存在严重缺陷

3. **品牌注意事项**：
   - XFX 需强制 UEFI 模式（BIOS 中关闭 CSM）
   - MSI Navi 显卡因 VBIOS 定制问题易导致黑屏

4. **幽默风格处理**：
   - 保留原文本调侃语气（如「专利技术」讽刺性表述）
   - 梗图（WebDrivers.gif）链接保留，增强文档趣味性

> 附：Nvidia 用户经典三连问  
> 「驱动有了吗？」「WebDriver 还能用吗？」「Metal 加速正常吗？」  
> —— 答案永远是：**放弃吧，少年** 💀
