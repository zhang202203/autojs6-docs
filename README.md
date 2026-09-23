# AutoJs6 知识库

AutoJs6 官方文档（https://docs.autojs6.com）的完整本地化编译版，供编写 AutoJs6 脚本时检索与引用。

- 建立时间：2026-09-22
- 文档基线：上游 v6.7.0（2026-03-14）
- 原文规模：131 份文档 / 2.0 MB，API 条目 2444 条
- 上游项目：https://github.com/SuperMonster003/AutoJs6

## 文件清单

| 文件 | 覆盖内容 |
| --- | --- |
| [00-导航.md](00-导航.md) | 先看这篇：知识库怎么用 + 高频陷阱速记 |
| [01-入门-运行环境与脚本基础.md](01-入门-运行环境与脚本基础.md) | Rhino 引擎 / ES 支持范围 / CommonJS / 全局对象清单 |
| [02-UI自动化-选择器控件无障碍.md](02-UI自动化-选择器控件无障碍.md) | 无障碍服务 / 选择器链式调用 / 阻塞风险 / 坐标与 Root |
| [03-脚本引擎-线程引擎事件.md](03-脚本引擎-线程引擎事件.md) | threads / engines 执行配置 / 死锁警告 |
| [04-图像-颜色-视觉识别.md](04-图像-颜色-视觉识别.md) | 截图权限 / 找色阈值 / colors / OCR / YOLO |
| [05-文件-存储-网络-数据库.md](05-文件-存储-网络-数据库.md) | files / storages / http / sqlite / zip |
| [06-文档总目录131页.md](06-文档总目录131页.md) | 官方 9 大分组目录，附摘要与 API 数量 |
| [07-API速查表-2444条.md](07-API速查表-2444条.md) | 全量 API 签名速查，含所有重载与最低版本 |
| [RELEASES.md](RELEASES.md) | 上游版本历史（Release Notes 正文，不含 APK），按版本反查 API 新增 / 变更 / 废弃 |

## 怎么用

写脚本时的固定路径：**速查表找 API → 官方文档核对 → 按场景查主题页**。

1. 在 `07-API速查表-2444条.md` 里搜 API 名，确认它存在、签名和所需最低版本。
2. 涉及参数个数与顺序、返回值类型、默认值时，点进官方原文核对，别只信摘要。
3. 系统性了解某个主题时，看 01–05 的主题页。

## 高频陷阱

- `untilFindOne()` / `untilFind()` 会永久阻塞，等价于 `findOne(-1)`
- `images.requestScreenCapture()` 同步方法不能在 UI 线程调用，UI 模式用 `...Async()`
- 找色 `threshold` 默认 `4`，与 `similarity` 互斥，不可同时传
- `threads.start()` 脚本退出时返回 `undefined`，需判空
- ES6 仅部分支持（ES5 全支持），`Promise` / `class` 等需实测

完整清单见 [00-导航.md](00-导航.md)。

## 引用方式

- 在线直链：`https://raw.githubusercontent.com/zhang202203/autojs6-docs/main/07-API速查表-2444条.md`
- CDN：`https://cdn.jsdelivr.net/gh/zhang202203/autojs6-docs@main/07-API速查表-2444条.md`

供 AI 检索时，建议先取 `00-导航.md` 和 `06-文档总目录131页.md` 定位，再取具体文件，避免整库加载。

## 维护

官方文档持续更新。需要同步时重新抓取原文并重新生成速查表即可。
