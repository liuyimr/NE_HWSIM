# NE_HWSIM

**华为 VRP 网络实训模拟器 · 就一个 HTML 文件，双击就能用。**

不用装 eNSP、不用装 GNS3、不用装 Java、不用装任何东西。没有后端、没有账号、不用联网。
把 `NE_HWSIM.html` 拖给学生，双击打开，就能开始敲交换机命令。

---

## 30 秒上手

| 步骤 | 做什么 |
|---|---|
| **1** | 下载 `NE_HWSIM.html`（右上角绿色 `Code` → `Download ZIP`，或直接点文件再点下载按钮） |
| **2** | **双击它** —— 用 Chrome / Edge 打开 |
| **3** | 已经自动搭好一套 VLAN 实验拓扑，点 **「开始配置」** 就能动手 |

就这三步。没有第 4 步。

> 发给学生：微信、QQ、U 盘、班级群，随便怎么传都行。存到桌面，双击打开。
> 文件必须保留 `.html` 后缀。建议用 Chrome 或 Edge，Firefox 也可以。

---

## 里面有什么

零安装是重点，功能不含糊：

- **8 套现成实训实验**：VLAN 基础 / Trunk 跨交换机 / 三层交换互通 / 静态路由 / OSPF / DHCP /
  **ACL 访问控制** / **NAT 网络地址转换**
- **真实的华为 VRP 命令行**：用户视图 → 系统视图 → 接口视图 → VLAN 视图 → **端口组视图** → ACL 视图 →
  **NAT 地址池视图** → OSPF 区域视图，**一级一级进入、`quit` 一级一级退出**，和真机一个规矩
- **真实的报错风格**：敲错了会出 `^` 精确指到出错的那个词，措辞和真机一致
- **真实的交互**：`save` 会问你 `(y/n)[n]`，再问你文件名——跟真机一模一样
- **批量配端口**：`interface range ge 0/0/1 to ge 0/0/5`、`port-group group-member ... to ...`（临时端口组）、
  `port-group 1`（命名端口组，写进配置）三种真机写法都有
- **拖拽搭拓扑**：4 种设备（S5700 三层交换 / S3700 二层交换 / AR6121 路由器 / PC），点两个端口就完成连线
- **配置自动保存在浏览器里**，关掉再打开还在
- **「导出配置」 / 「导入配置」**：导出成 txt 交给老师检查；导入时能读回来。
  画布上没有的设备会**按型号自动新建**，导入后弹报告逐条列出「哪些生效、哪些没生效、报错原文是什么」
- **命令行面板可展开 / 收起**：顶栏按钮、面板右上角，或 `Ctrl + \`` 都行

支持的配置范围：VLAN、Access/Trunk/Hybrid 端口、MAC 地址表、STP/RSTP、直连与静态路由、OSPF 单区域、
DHCP 地址池、**ACL（基本/高级，含隐含 deny all、源+目的+协议匹配、入/出双向、可绑物理口或 Vlanif）**、
**NAT（Easy IP / 地址池）**、链路聚合 Eth-Trunk、端口安全。
`display` 系列也齐：`display vlan` / `display interface` / `display port vlan` / `display acl` /
`display nat session all` / `display port-group all` / `display ip routing-table` /
`display ospf interface` / `display this` 等等。

---

## 谁适合用

- **网络课老师** —— 学生人手一份，不用折腾机房环境，不用申请 eNSP 授权
- **备考 HCIA / HCIP 的同学** —— 随时打开就能练命令，不用等虚拟机启动
- **自学者** —— 想搞明白 VLAN 和 OSPF 到底怎么回事，最好的办法是自己敲一遍

---

## 为什么是单文件

因为"让学生愿意用"这件事，最大的敌人是安装步骤。

eNSP 要装 VirtualBox，GNS3 要配镜像，虚拟机镜像动辄几个 GB，还得看电脑配置。
很多学生卡在第一步就放弃，然后就没有然后了。

NE_HWSIM 的判断是：**先把门槛降到零**。一个 230 KB 的 HTML 文件，
发过去、双击、开始练——整个过程不需要任何解释。

---

## 最近更新

**v1.1.0**

- 新增两个实验：**实验七 · ACL 访问控制**、**实验八 · NAT 网络地址转换**
- 新增 **批量配端口**：`interface range` / `port-group group-member` / `port-group <名字>`
- ACL 补全：**源+目的+协议**匹配、**隐含 `deny all`**、`traffic-filter` **出方向**、**可绑 Vlanif**
- 新增 **NAT**：Easy IP、`nat address-group` 地址池、`display nat session all`
- 新增 **「导入配置」**（导出的 txt 可读回，缺失设备按型号自动新建）
- 命令行面板可**展开 / 收起**（顶栏按钮、面板按钮、`Ctrl + \``）
- PC 卡片尺寸收紧（从 260×97 收到 126×57，PC 只有一个网口）
- 修正连线端点长期存在的 1px 偏移，现在与端口中心像素级对齐

**v1.0.0** —— 首个公开版本

---

## 反馈与交流

- 发现 Bug 或有建议，欢迎开 [Issue](../../issues)
- 如果是教学场景的需求（比如想要某个特定实验、想改题目），也欢迎提出来

---

## 许可

MIT License —— 随便用，商用也行，改了也不用说。详见 [LICENSE](LICENSE)。

简单说就是：**你可以拿去发给你的学生、你的培训班、你的同事，不用问我。**

---

## 关于

**新易科技工作室 NewE** · 福州
作者：Liuyi · yimr@sohu.com

做工业自动控制与楼宇智能化的，这个是给网络教学做的小工具。

---

## 免责声明

本项目为**非官方**教学演示工具，与华为技术有限公司（Huawei Technologies Co., Ltd.）
**无任何关联**，未获得其任何形式的授权、赞助或背书。

"Huawei"、"HUAWEI"、"VRP"、"Versatile Routing Platform"、"eNSP" 等为其各自权利人的商标或注册商标。
本项目中出现这些名称，**仅用于说明模拟器所兼容 / 模仿的命令语法风格**（描述性合理使用）。

模拟器的命令回显（例如 `display version` 的输出格式）为**自行编写的模拟内容**，
不包含华为公司的任何源代码、固件、文档或二进制文件。

---

*A simple HTML file for learning Huawei VRP. No installation, no setup — just double-click and practice.
Licensed under MIT. Made by [NewE](mailto:yimr@sohu.com) (Fuzhou, China).*
