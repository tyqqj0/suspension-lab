# 钛3 公开模型资产 & 跨平台采集约束 — 外部调研笔记

- 调研日期：2026-10-14（第二轮修订：2026-10-14）
- 调研人：Life~（仅做外部资料调研，不含架构决策）
- 目标车型：方程豹 钛3 闪充版四驱（Fangchengbao Tai 3 / Titanium 3 / 海外别称 Leopard 3），比亚迪子品牌紧凑型纯电 SUV
- 边界：不登录、不购买、不下载模型；未建仓、未安装软件
- 命名陷阱（需长期注意）：官方/维基页名为 **Fangchengbao Tai 3**，同一车型在英文渠道被称为 *Titanium 3* 或 *Leopard 3*；而 **钛7 / Tai 7 / Ti7 / Titanium 7** 是另一款车，**豹3（Bao 3 / Leopard 3 概念车）** 与 2025 上市的钛3 存在名称交叉，二者不是同一车。维基条目：<https://en.wikipedia.org/wiki/Fangchengbao_Tai_3>
- **结论强度约定**：本文件区分三档 —— **已核实**（有一手页面证据）／**未搜到**（本轮检索未出现，不等于不存在）／**未验证**（抓取被阻塞，无法定论）。

---

## 1. 查找范围（实际检索过的入口）

| 类别 | 入口 | 结果 |
|---|---|---|
| 官方 | 方程豹官网 首页/钛3 页/参数配置页 <https://www.fangchengbao.com/tai3.html>、<https://www.fangchengbao.com/disposition-tai3.html> | 只有产品图、参数表、金融政策。**本次访问的官方页面未发现 3D/CAD/glTF/URDF 下载入口**（不因此断言官方不存在此类资产） |
| 通用 3D 商城 | CGTrader BYD 目录（339 项）<https://www.cgtrader.com/3d-models/byd> | 本次浏览的目录页中 **未发现钛3**；见到豹5、鲨鱼6、钛7 等 |
| 通用 3D 商城 | 3DExport BYD 目录（174 项）<https://3dexport.com/3d-models/byd> | **未发现钛3**；见到 "BYD Fang Cheng Bao Tai 7"（$69）、"BYD Ti 7 2027"（$69）、"BYD T3 2026"（注意：T3 是**厢式货车**，非钛3）、豹5/豹8 |
| 通用 3D 商城 | TurboSquid BYD 搜索 | **未验证**。自动化浏览器超时（见 §5） |
| 模型社区 | Sketchfab | **已核实（第二轮补做）**：用自动化浏览器直接打开搜索结果页，`q=tai 3 fangchengbao`、`q=fangchengbao`、`q=byd leopard 3`、`q=byd titanium` **均返回 "No results"**；对照组 `q=byd` 有结果，说明搜索链路正常、不是被拦截导致的假空 |
| 模型社区 | MakerWorld 3D 打印目录（`比亚迪 3d print model`） | 有 "方程豹钛7 1:50模型" 等**打印件（STL/打印类）**，**未发现钛3**；打印件不构成整备质量/悬架可用的外观资产 |
| 车辆动力学/仿真 | GitHub 检索 URDF / vehicle dynamics / BYD / suspension | **未搜到**任何比亚迪·方程豹车型的 URDF 或 Chrono/动力学模型 |
| 中文素材/打印站 | 站内检索（迪威模型 3dwhere.com、爱给网、创想云、Enjoying3D 等为搜索命中的站点列表） | **未发现钛3**（仅取得站点入口，未逐站遍历） |
| 许可/正版素材 | 搜索"钛3 3D模型 下载 素材" | 只回落到官网、资讯、商城目录，**无版权可查的钛3模型** |

---

## 2. 找到的候选（含"不是"的对照项）

### 2.1 与钛3 车型精确匹配、但**不是 3D 模型**

- **标题**：BYD Fangchengbao Tai 3 (2025 – 2026) (CS) (ES) Full Car Body PPF Cutting Template
- **发布页**：<https://armobileskin.com/product/byd-fangchengbao-tai-3-2025-2026-cs-es-full-car-body-ppf-cutting-template/>
- **车型匹配**：是（明确标注 Tai 3 2025–2026），但**不是 3D 资产**
- **格式**：ZIP，内含 PDF / CDR / SVG / DXF / EPS / AI / PLT —— **2D 矢量贴膜裁切图**
- **价钱**：付费（价格需进商品页确认；本次未登录未购买）
- **许可**：**未确认**。站点级别未给出可再分发/可嵌入网页的授权说明，不得据此推断可再分发

### 2.2 同品牌、车型不同的付费外观模型（仅作品牌/制作质量水位参考）

- **BYD Fang Cheng Bao Tai 7** — <https://3dexport.com/3d-model-byd-fang-cheng-bao-tai-7-668907>（$69.00，含 C4D/MAX/OBJ/FBX/MA/LWO/3DS/3DM/STL）
- **BYD Ti 7 2027** — <https://3dexport.com/3d-model-byd-ti-7-2027-669359>（$69.00）
- **2026 BYD Ti7 Titanium7 Plug-in Hybrid with Interior** — <https://www.cgtrader.com/3d-models/car/suv/2026-byd-ti7-titanium7-plug-in-hybrid-with-interior>（$179，含内饰）
- **2023 BYD FANGCHENGBAO BAO5 / Leopard 5 Flagship Edition** — <https://www.cgtrader.com/3d-models/car/suv/2023-byd-equation-leopard5-flagship-edition>（$49）
- **BYD Fang Cheng Bao Leopard 5 2025** — <https://3dexport.com/3d-model-byd-fang-cheng-bao-leopard-5-2025-655653>（$69.00）
- **BYD Fang Cheng Bao Leopard 8** — <https://3dexport.com/3d-model-byd-fang-cheng-bao-leopard-8-645186>（$69.00）
- **2027 BYD FANGCHENGBAO SHARK DMO with interior** — <https://www.cgtrader.com/3d-models/car/suv/2027-byd-fangchengbao-shark-dmo-with-interior>（$169）
- **说明**：这些**都不是钛3**，也不应被理解为"可改造成钛3"或"平台资产可复用"——仅记录同品牌付费模型的存在与价位水位。
- **许可**：**未确认（逐项未核实）**。平台默认授权通常为"Royalty Free、禁止再分发原始模型文件"，但各商品页可覆盖不同条款，必须逐条打开该商品的 License 段确认。**免费可下载 ≠ 开源**；本轮未发现任何带 CC/开源许可的车型模型。

### 2.3 结论边界

- **已核实**：本次访问的方程豹官网页面（首页、钛3 页、配置页）未发现 3D/CAD 资产下载入口。
- **已核实**：Sketchfab 站内以 `fangchengbao` / `byd leopard 3` / `byd titanium` / `tai 3 fangchengbao` 检索**均无结果**（有对照组排除拦截误判）。
- **未搜到（≠不存在）**：钛3 的外观 3D 模型（glTF/GLB/FBX/OBJ/Blend/CAD）、参数化车辆动力学模型（Chrono/URDF）。仍可能存在于 TurboSquid（**未验证**）、国内素材站（**未逐站遍历**）、付费定制渠道、以及未检索的 CAD 交易渠道。

---

## 3. 许可证核实（逐条）

| 资产 | 许可证状态 | 依据 |
|---|---|---|
| 官网钛3 相关图片/参数 | 无资产可谈许可；**未确认** | 本次访问的官网页面未发现下载区 |
| armobileskin PPF 模板 | **未确认**（付费、疑似个人施工用途） | 商品页未见显式再分发授权 |
| CGTrader / 3DExport 付费车模 | **未确认**，需逐项查该商品 License 段 | 目录页无许可信息 |
| MakerWorld 打印模型 | **未确认**；平台通常区分 CC 与非商用条款，需逐项查 | 目录页无许可信息 |

**本轮没有发现任何"允许修改 / 允许再分发 / 允许嵌入公开网页"的钛3模型资产。凡未逐项核实，一律标"未确认"。**

---

## 4. 工具事实（一手来源核实）

### 4.1 Rapier — 有 JS/WASM 绑定，raycast vehicle 为单刚体无独立车轮质量

- 官方文档明确：Rapier 提供 vehicle controller，**实现是从 Bullet 的 `btRaycastVehicle` 移植而来**；"The vehicle is a **single rigid-body** modeling its chassis, and its wheels are **only represented by ray-casts** pushing that body along a spring-like suspension."
- 官方同时说明：每个车轮"there is **no actual per-wheel rigid-bodies**"，车轮状态（接地、悬架压缩量、转动角）只能从 controller 读取，用于渲染。
- 创建方式：`world.createVehicleController(chassis)`，逐轮 `addWheel(position, suspensionDirection, axle, restLength, radius)`，再设 `setWheelSuspensionStiffness / Compression / Relaxation`；驱动靠 `setWheelEngineForce / setWheelSteering / updateVehicle(dt, ...)`。
- 来源：<https://rapier.rs/docs/user_guides/javascript/vehicle_controller/>（JS 版用户指南，术语与 API 均为官方）
- **模型形式（事实层）**：**单个车身刚体 + 无独立车轮质量的射线悬架**。其限制来自这一模型形式本身，与路面/地形数据是否粗糙无关。

### 4.2 Project Chrono — C++ 多体/多物理，含 Vehicle 模块与 Python 接口，不是浏览器库

- Chrono::Vehicle 是 Chrono 的模块，**模板化地面车辆建模与仿真**；构建时需 `CH_ENABLE_MODULE_VEHICLE` 为 on，可用 conda 的 PyChrono 包，Python demos 位于 `src/demos/python/vehicle/`。来源：<https://api.projectchrono.org/module_vehicle_installation.html>
- PyChrono 教程确有多条 Vehicle 示例（HMMWV、CityBus、UAZ、MAN 10t、以及用 JSON 完整描述的 `demo_VEH_WheeledJSON.py`）。来源：<https://api.projectchrono.org/tutorial_table_of_content_pychrono.html>
- 官方预置车型库（HMMWV、FEDA、Sedan、CityBus、FMTV、MAN、UAZ、Gator、KRAZ、RC-car、generic 等）在**本次查阅的目录页中未发现钛3或任何中国乘用车车型**。来源：<https://api.projectchrono.org/vehicle_models.html>
- 官方还说明：碰撞用凹网格较慢且不稳健，常用做法是"**精细网格只做可视化，碰撞用少量基本体**"，网格格式为 `.obj`（可由 Blender/Maya/CAD 导出）。来源同上 PyChrono 教程（`demo_MBS_collision_trimesh.py` 条目）
- **结构含义（事实层）**：Chrono 是**本地/桌面侧 C++/Python 引擎**，官网文档没有任何浏览器/WASM 发行形态的描述。**不是开箱即用的浏览器库。**

### 4.3 Capacitor Motion 插件 — 官方明说"当前用 Web API 实现"

- 官方文档原文：**"This plugin is currently implemented using Web APIs."**（`@capacitor/motion` v8）
- 其权限流程就是 Web 侧 API：`DeviceMotionEvent.requestPermission()` / `DeviceOrientationEvent.requestPermission()`，官方示例要求**在用户手势（如按钮点击）中触发**；官方把读者引向 MDN 的 `DeviceMotionEvent` / `DeviceOrientationEvent` 两类 Web API 页面理解数据。
- 数据字段就是 Web 同名对象：`acceleration`、`accelerationIncludingGravity`（m/s²）、`rotationRate`（alpha/beta/gamma，度/秒）、`interval`（毫秒）。
- 来源：<https://capacitorjs.com/docs/apis/motion>
- **关键结论：Capacitor 的 Motion 插件不会把"套壳"变成原生后台 IMU。它没有原生后台采样承诺，也没有独立于 Web 时间线的采样节拍。**

### 4.4 Web 端传感器的一手限制

- MDN：`DeviceMotionEvent` **仅在 secure context（HTTPS）可用**；官方给出的权限方式是 `requestPermission()` 返回 `"granted"` 后才可读加速度计与陀螺仪。来源：<https://developer.mozilla.org/en-US/docs/Web/API/DeviceMotionEvent>
- **该权限闸门并非所有浏览器/平台统一强制**：`requestPermission` 是特定平台（主要为 iOS Safari 系）引入的机制；**是否出现、是否必须调用、以何种方式授权，依浏览器与平台而异**，不能假设"所有浏览器都必须走同一个授权流程"。来源同上（MDN 该页把 `requestPermission()` 列为静态方法，并在兼容性/说明中体现平台差异）
- MDN 同页提示 **Firefox 与 Chrome 对坐标系处理不一致**，同一份数据的跨浏览器语义不统一。来源同上。
- 关于**锁屏/后台持续采样**：Capacitor 文档与 MDN 均**未给出任何后台或锁屏采样的可用性声明** → 在 Web/PWA 路径上**无官方依据、不能作为可承诺能力**（本次未找到任何官方页面承诺该行为）。

---

## 5. 缺口与未完成项（如实记录）

1. **TurboSquid**：**未验证**。具体失败路径——自动化浏览器（agent-browser headless）打开 TurboSquid 搜索页两次均超时（`document.body.innerText.length > 800` 未满足）；按 agent-browser 规范应升级到真实 Chrome over CDP，但**本机未安装 Google Chrome**（`/Applications/Google Chrome.app` 不存在），CDP 路径不可用；未执行 `agent-browser install`（会下载 Chrome for Testing，属安装行为，超出本次授权）。浏览器进程已清理。
2. **国内素材/打印站**：仅取得站点入口列表，**未逐站遍历**。若需定论，应逐站站内检索"钛3 / 方程豹"。
3. 所有付费商品的**逐项许可条款未核实**（未打开商品详情页 License 段）。
4. 未检索 CAD 交易渠道（GrabCAD 类）与学术/自动驾驶数据集中的中国车型。
5. 官网其他子域是否存在配置器类 3D 资产：**本次访问的页面未发现**，未做子域枚举。

---

## 6. 一句话结论

**本次检索未确认公开网络上存在钛3（Tai 3 / Titanium 3）的可授权 3D 外观模型，也未检索到任何比亚迪·方程豹车型的车辆动力学/URDF 模型；本轮唯一精确匹配钛3 的资产是一份 2D 贴膜裁切图（付费、许可未确认）。工具侧已核实：Rapier 的车辆控制器是"单个车身刚体 + 无独立车轮质量的射线悬架"，Chrono::Vehicle 是桌面 C++/Python 引擎（文档无浏览器/WASM 发行形态），Capacitor Motion 官方自述为 Web API 实现且其权限闸门依浏览器平台而异 —— 因此"Capacitor 套壳"不改变 Web 采集的本质约束，锁屏后台 IMU 采样无官方可承诺依据。本结论限于本轮已实际访问的来源，不构成"公开网络不存在"或"所有比亚迪车型均无模型"的断言。**
