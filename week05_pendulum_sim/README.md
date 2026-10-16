# Week05 · 意图造物与 ReAct 闭环编程实验

> 课程：人机协同程序设计（南昌大学）
> 实验形式：个人独立上机实验（HOTL 模式）
> 实验日期：2026-10-16

---

## 一、实验者信息

| 项目 | 内容 |
| --- | --- |
| 姓名 | 张紫怡 |
| 学号 | 5907126089 |
| 班级 | <!-- 选填 --> |

---

## 二、无菌工作区（Sterile Workspace）就绪状态

本目录为第 5 周实验的**独立无菌子模块**，与课程主仓库中其他周次的文件完全隔离，不污染任何既有内容。

- [x] 已在课程主仓库根目录下创建专属目录 `week05_pendulum_sim/`
- [x] 目录内文件自包含，不依赖外部资源
- [x] Git 基线已锁定（本仓库首个 commit）
- [x] 老师提供的演练代码已归档至 `starter_code/03_buggy_practice/`

---

## 三、任务进度

| 任务 | 内容 | 状态 |
| --- | --- | --- |
| 任务一 | 初始化工程与创建无菌工作区 | ✅ 完成 |
| 任务二 | 单摆物理模拟器 MVP（`index.html`） | ⬜ 待完成 |
| 任务三 | 参数滑块绑定与实时物理交互 | ⬜ 待完成 |
| 任务四 | 控制台报错捕获与 ReAct 闭环自愈 | ⬜ 待完成 |
| 任务五 | 进阶挑战探索与三反思 | ⬜ 待完成 |

---

## 四、目录结构

```
week05_pendulum_sim/
├── README.md                              # 本文件：实验者信息与工作区状态
├── index.html                             # 主交付物（单文件应用，任务二起创建）
└── starter_code/
    └── 03_buggy_practice/
        └── index.html                     # 任务四故障演练代码（含 ReferenceError 埋点）
```

### 关于演练代码的已知故障点（任务四用）

`starter_code/03_buggy_practice/index.html`：

- 第 168 行按钮绑定 `onclick="resetAnimation()"`
- 第 214 行实际定义的函数名却是 `resetSimulationState()`
- 后果：点击"重置摆动"按钮触发 `Uncaught ReferenceError: resetAnimation is not defined`

---

## 五、物理模型（任务二、三参考）

单摆角加速度微分方程：

```
d²θ/dt² = -(g / L) · sin(θ) - k · ω
```

| 符号 | 含义 | 取值 |
| --- | --- | --- |
| θ | 摆角（弧度） | 初始 45° |
| L | 摆长（像素） | 100 ~ 350 px |
| g | 重力加速度 | 1.0 ~ 25.0 |
| k | 空气阻尼系数 | 0.000 ~ 0.010 |
| ω | 角速度 | — |

---

## 六、提交记录

| Commit | 说明 |
| --- | --- |
| （首个） | `feat(week05): init pendulum experiment workspace` |
