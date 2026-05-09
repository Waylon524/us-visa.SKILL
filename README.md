# 美签面试官 · US Visa Interview Simulator

模拟美国非移民签证（B1/B2）面试的 Claude Code Skill。以真实签证官的风格进行一对一追问，帮你在面签前发现回答中的漏洞和风险点。

## 功能

- **真实模拟** — 按签证官逻辑简短、直接、连续追问，不背答案
- **双语面签** — 支持中文面签和英文面签两种模式
- **风险识别** — 自动检测 214(b)、221(g)、信息不一致、移民倾向、诚信风险
- **结构化评估** — 面试结束给出：通过/暂不通过/不通过 + 风险等级 + 主要原因 + 最危险回答 + 改进建议
- **两种模式**
  - **准备模式** — 梳理材料、流程、常见拒签点（含 EVUS 提醒）
  - **练习模式** — 完整角色扮演面试

## 安装

```bash
claude plugins install Waylon524/美签面试官.SKILL
```

## 使用方式

在 Claude Code 中直接说：

```
模拟一轮美签面试
```

或者：

```
先告诉我 B1/B2 面签要准备什么
```

Skill 会先确认你的资料呈递情况和语言偏好，再进入正式面试。

## 示例

### 练习模式

```
用户：我们来练一轮。32岁已婚，外企产品经理6年，月薪3万，
      暑假带妻子去洛杉矶旧金山12天，费用自理。

助手：在开始前，你有没有想作为面签材料呈递的资料？
     你想练习英文面签还是中文面签？

用户：中文面签。没有资料。

助手：好，现在开始模拟面签。
     你为什么去美国？
     → 旅游...
     你计划待多久？
     → 12天...
     谁承担这次旅行的费用？
     → ...

（面试结束后）
### 模拟结论
- 是否能通过：能
- 模拟评级：模拟通过
- 风险等级：低
...
```

### 准备模式

```
用户：先告诉我 B1/B2 面签要准备什么

助手：（列出 DS-160、护照、照片、214(b) 常见拒签原因、EVUS 要求等）
     要不要现在开始一轮模拟面签？
```

## 目录结构

```
SKILL.md                          # Skill 定义与面试逻辑
README.md                         # 本文件
references/
  official-requirements.md         # 美国国务院官方要求速查
evals/
  evals.json                       # 评估用例
```

## 评估维度

面试中重点审查五个维度：

| 维度 | 说明 |
|------|------|
| 目的真实性 | 赴美活动是否属于 B1/B2 允许范围，理由是否具体可信 |
| 临时性与回国约束 | 工作、学业、家庭、资产等是否形成真实回国动机 |
| 财务可信度 | 资金来源是否稳定、合法、足以支持旅行 |
| 信息一致性 | 回答是否与 DS-160、前文、常识逻辑一致 |
| 历史风险 | 既往拒签、逾期停留、虚假陈述等 |

## 风险信号

出现以下情况默认标记为高风险并优先深挖：

- 赴美目的说不清
- 行程、时长、预算模糊
- 无稳定工作/收入但计划长时间赴美
- 美国有亲密伴侣或大量直系亲属，中国约束弱
- 有拒签史但说不清原因
- 赴美工作、生子、长期停留、转身份倾向
- 口头版本与 DS-160 关键字段冲突
- 暗示要隐瞒真实目的或包装材料

## 免责声明

- **这是模拟判断，不是美国国务院、使领馆或领事官员的正式决定**
- 不承诺"包过"，不暗示可以规避审查
- **不帮助用户编造工作、资产、婚姻、行程或其他虚假信息**
- 结论基于用户回答质量，不因"材料多"就默认能过
- 真实签证结果只能由美国领事官员根据面谈、DS-160、指纹和个案材料决定

## 参考来源

评估逻辑基于美国国务院公开信息，详见 [references/official-requirements.md](references/official-requirements.md)，官方来源包括：

- [DS-160 说明与 FAQ](https://travel.state.gov/content/travel/en/us-visas/visa-information-resources/forms/ds-160-online-nonimmigrant-visa-application.html)
- [Visitor Visa 页面](https://travel.state.gov/content/travel/en/us-visas/tourism-visit/visitor.html)
- [Visa Denials](https://travel.state.gov/content/travel/en/us-visas/visa-information-resources/visa-denials.html)
- [China Reciprocity Schedule](https://travel.state.gov/content/travel/en/us-visas/Visa-Reciprocity-and-Civil-Documents-by-Country/China.html)
- [EVUS FAQ](https://www.cbp.gov/document/publications/electronic-visa-update-system-evus-advertisements)

## License

MIT
