# 🛂 美签面试官 — 你的 AI 签证官

> *"下一位！"* — 现在轮到你了。

一个 Claude Code Skill，用真实签证官的风格和你一对一模拟美国 B1/B2 面签。不用背答案、不用花钱找中介、不用在使馆窗口前手心冒汗——先在终端里被 AI 签证官"审"一轮，发现回答里的坑，再去面对真正的窗口。

---

## 为什么你需要这个？

签证官只有 2-3 分钟来决定你的命运。你准备了一摞材料，但可能开口第一句话就踩了雷。

这个 Skill 不是教你"背标准答案"——而是像真正的签证官一样，用简短、直接、连续追问的方式，把你回答中的模糊、矛盾、风险点通通挖出来。

**在 AI 面前被拒，总好过在使馆窗口被拒。**

---

## 它能做什么

- **真·窗口体验** — 简短追问，不废话，不教条，跟真签证官一个风格
- **双语面签** — 想练英文面签还是中文面签？你说了算
- **火眼金睛** — 自动揪出 214(b) 移民倾向、221(g) 材料不全、信息前后矛盾、诚信风险、行程说不清
- **结构化打分** — 面试结束给你一份"模拟判决"：通过/还能抢救/没戏 + 风险等级 + 问题在哪 + 怎么改
- **两种模式随时切**
  - `准备模式`：先告诉我 B1/B2 要准备什么材料，有什么坑
  - `练习模式`：直接开始，我扮演签证官

---

## 安装

### 方法一：安装到当前用户（全局可用）

```bash
# 克隆到 Claude Code 用户 skills 目录
git clone https://github.com/Waylon524/us-visa.SKILL.git "$HOME/.claude/skills/us-visa"
```

安装后重启 Claude Code 即可使用，所有项目都能调用。

### 方法二：安装到当前项目（仅项目内可用）

```bash
# 克隆到项目的 .claude/skills 目录
git clone https://github.com/Waylon524/us-visa.SKILL.git .claude/skills/us-visa
```

适合只想在特定项目中使用，或团队共享 skill 的场景。

### 方法三：直接下载

不用 git 的话，直接下载 ZIP 解压到 `~/.claude/skills/us-visa/` 或项目的 `.claude/skills/us-visa/` 即可。

---

## 使用方式

打开 Claude Code，直接说人话就行：

```
模拟一轮美签面试
```

或者：

```
先告诉我 B1/B2 面签要准备什么
```

Skill 会自动引导你——先确认你有没有材料要呈递、想用英文还是中文面签，然后进入正式面试。

---

## 预览

### 练习模式

```
你：我们来练一轮。32 岁已婚，外企产品经理 6 年，月薪 3 万，
    暑假带妻子去洛杉矶和旧金山 12 天，费用自理。

AI：在开始前，你有没有想作为面签材料呈递或供我核验的资料？
    你想练习英文面签还是中文面签？

你：中文面签。没有资料。

AI：好，现在开始模拟面签。
    你为什么去美国？
    你计划在美国待多久？
    你现在做什么工作？
    ...

（面试结束后）

AI：  ### 模拟结论
      - 模拟评级：模拟通过 ✅
      - 风险等级：低
      ### 主要原因
      1. 赴美目的具体、可信
      2. 工作稳定，收入可支撑行程
      3. 已婚有家庭，回国约束明确
      ...
```

### 准备模式

```
你：先告诉我 B1/B2 要准备什么

AI：（列出 DS-160、护照、照片要求、214(b) 常见拒签原因、
     EVUS 提醒、不同使领馆等位时间等）
     要不要现在开始一轮模拟面签？
```

---

## 面试官审什么

| 维度 | 灵魂拷问 |
|---|---|
| **目的真实性** | 你说去旅游——去哪几个城市？住哪？玩什么？行程能不能说清楚？ |
| **回国约束** | 你在中国有工作、有家人、有房子吗？凭什么让我相信你会回来？ |
| **财务可信度** | 钱够吗？钱哪来的？银行流水能看吗？ |
| **信息一致性** | 你现在说的，跟 DS-160 填的一样吗？跟刚才说的矛盾吗？ |
| **历史风险** | 被拒过吗？逾期待过吗？材料改过吗？ |

---

## 什么回答会让 AI 签证官皱眉

- "我就想去看看" — 但说不出看什么
- "大概待一两个月吧" — 行程和预算完全说不清
- "我朋友出钱" — 但说不清朋友是谁、什么关系
- 没工作、没收入、没家庭，但计划赴美待很久
- 美国有伴侣/大量亲属，中国这边什么羁绊都没有
- 被拒过但"不记得原因"——签证官系统里是有记录的
- 口头回答跟 DS-160 对不上
- 暗示"我其实想去那边找工作/生孩子/移民"

出现以上任何一条，AI 签证官会立刻追问，直到你解释清楚为止。

---

## 项目结构

```
美签面试.skill/
├── SKILL.md              # Skill 定义 & 完整面试逻辑
├── README.md             # 你在看这个
├── LICENSE               # MIT
├── references/
│   └── official-requirements.md  # 美国国务院官方要求速查（截至 2026-05）
└── evals/
    └── evals.json         # 评估用例
```

---

## 免责声明

> **这不是美国国务院、使领馆或领事官员的正式决定。绝对不承诺"包过"。**

- 这是一个 AI 模拟工具，用于面试练习和自我检查
- 不帮助用户编造、修改、包装任何虚假信息
- 真实签证结果只能由美国领事官员根据面谈、DS-160、指纹和个案材料决定
- 面签通过不等于一定入境；最终入境许可由 CBP 在口岸决定

---

## 参考来源

评估逻辑基于美国国务院公开信息：

- [DS-160 说明与 FAQ](https://travel.state.gov/content/travel/en/us-visas/visa-information-resources/forms/ds-160-online-nonimmigrant-visa-application.html)
- [Visitor Visa](https://travel.state.gov/content/travel/en/us-visas/tourism-visit/visitor.html)
- [Visa Denials](https://travel.state.gov/content/travel/en/us-visas/visa-information-resources/visa-denials.html)
- [China Reciprocity Schedule](https://travel.state.gov/content/travel/en/us-visas/Visa-Reciprocity-and-Civil-Documents-by-Country/China.html)
- [EVUS FAQ](https://www.cbp.gov/document/publications/electronic-visa-update-system-evus-advertisements)
- [Global Visa Wait Times](https://travel.state.gov/content/travel/en/us-visas/visa-information-resources/global-visa-wait-times.html)

---

## License

[MIT](LICENSE)
