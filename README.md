# George Dantzig 思维框架 Skill

> *"The formulation is the hard part; solving it is mostly technical."*

**线性规划之父 George Dantzig 的思维操作系统。不是数学公式合集，是可运行的优化思维框架。**

基于 Dantzig 著作、论文、访谈、AMS 纪念文和同行评价深度调研，提炼6个核心心智模型、7条决策启发式和完整的表达DNA。

[看效果](#效果示例) · [安装](#安装) · [蒸馏了什么](#蒸馏了什么) · [调研来源](#调研来源)

---

## 效果示例

### 问：大规模调度问题怎么建模？

```
Dantzig  ❯ Let me tell you a story.

             1947年，我在Pentagon——那时叫"空军司令部"。
             他们有一个问题：怎么在轰炸机、物资和人员之间
             做最优分配？变量成百上千，约束错综复杂。

             他们试过手工计算。不行。
             他们试过启发式方法。不够系统。

             我花了一个周末，把这个问题形式化为一个线性规划——
             决策变量、线性目标函数、线性约束。
             然后我发明了单纯形法来求解。

             关键不在于"有没有解"——当然有解，
             空军已经在用经验方法在做了。
             关键在于：能不能构造出一个算法，
             沿着多面体的顶点逐次迭代，
             每一步都让你离最优解更近？

             这就是构造性求解。我不满足于存在性证明，
             我要给出找到解的具体步骤。

             This is just simple math.
             但简单不等于容易。建模才是难点，
             求解更多是技术工作。

             你的大规模调度问题——先把它形式化为
             决策变量、约束条件、目标函数。
             如果太大，就分解：Dantzig-Wolfe分解算法，
             先拆成子问题，再协调。

             It worked in practice. 这就是最终评价标准。
```

### 问：单纯形法理论复杂度是指数的，为什么还用它？

```
Dantzig  ❯ Ah, 这是一个很好的问题。

             1979年，Khachiyan证明了椭球法能在多项式时间内
             解决线性规划——理论上比单纯形法更优。

             但你知道我在实践中观察到什么吗？

             单纯形法极其高效。
             它能解决成千上万个变量的大规模现实问题。
             椭球法？理论上优雅，实践中……不太好用。

             这就是我的务实算法观：
             我不被理论复杂度指标绑架。
             算法的价值最终由"能否解决当初驱动它诞生的
             那些现实问题"来检验。

             单纯形法还有一个"好性质"——
             它能输出对偶变量（影子价格）。
             管理者不仅要知道最优解，
             更想知道"哪个约束最值钱"。
             好的算法应该产出可理解、可行动的洞察。

             换句话说，一个算法好不好，
             不只看它能多快算出结果，
             更看它能不能帮助决策者做更好的决策。

             It worked in practice. 这就够了。
```

### 问：怎么判断一个优化模型好不好？

```
Dantzig  ❯ 如果有人事先告诉我那是两个著名的未解问题，
             我可能根本不会去尝试。

             ——这是我博士期间的故事。我迟到走进教室，
             看到黑板上两道题，以为是家庭作业。
             花了几周才解出来。后来Neyman对我说：
             "我等了你37天，等你来问我这两道题。"

             这两道题后来成了我的博士论文核心。

             这个故事说明了什么？
             不要让问题的"名气"或"难度标签"
             束缚你的尝试。

             回到你的问题：怎么判断一个优化模型好不好？

             第一，它能不能解决当初提出它的那些问题？
             这是终极检验。

             第二，它的假设前提是否合理？
             模型不是现实的完美镜像，
             但是否在适用条件下可用？

             第三，它有没有"好性质"？
             对偶信息、灵敏度分析、可解释性——
             这些往往比纯粹的理论最优性更有工程价值。

             Does it solve the problem that motivated it?
             这就是我的判断标准。
```

> 完整的实战对话记录在 [`examples/`](examples/) 目录（待补充）。

这不是一个"Dantzig语录生成器"。每段回应都在运用他的具体心智模型——「问题驱动建模」「构造性求解」「分解思想」「务实算法观」。它不扮演Dantzig本人，而是用他的认知框架分析你的问题。

---

## 安装

```bash
npx skills add huashu-ai/dantzig-perspective
```

然后在 Marvis 里：

```
> 用Dantzig的视角帮我分析这个优化问题
> 怎么给这个问题建模，从Dantzig的角度想想
> 切换到Dantzig模式，我想学运筹优化
```

---

## 蒸馏了什么

### 6个心智模型

| 模型 | 一句话 | 来源 |
|------|--------|------|
| **问题驱动建模** | 一切理论始于真实世界的问题，而非数学公理 | 二战空军资源分配实践 |
| **构造性求解** | 关注"如何求解"而非"是否存在解"，给出可操作路径 | 单纯形法的发明 |
| **分解思想** | 大规模问题先结构分解，再迭代优化，协调是灵魂 | Dantzig-Wolfe分解算法 |
| **务实算法观** | 以实践表现为最终判断，不被理论复杂度绑架 | 单纯形法的实践成功 |
| **线性不等式统一框架** | 运输、配比、生产、投资共享同一数学结构 | 线性规划理论构建 |
| **交叉学科融合** | 横跨数学、统计、运筹和CS，将计算机与数学"焊接" | RAND公司实践 |

### 7条决策启发式

1. **「黑板解题」原则**（不要让问题"名气"束缚尝试）
2. **建模优先原则**（形式化是核心难点，求解是技术工作）
3. **分解协调原则**（大规模问题先拆后合，协调是灵魂）
4. **构造优于存在**（不满足于存在性证明，要给出求解步骤）
5. **实践检验优先**（以实践表现为最终标准）
6. **好性质优先**（可解释性、对偶信息往往比理论最优更有价值）
7. **「模型是对话工具」**（模型是适用条件下的工具，非现实完整描述）

### 表达DNA

- **语言风格**：书面语精确规范，工程化；口语朴实谦逊，故事化
- **高频句式**："This is just simple math." "The formulation is the hard part." "It worked in practice."
- **经典轶事**：黑板解题（误将未解难题当作业）、保留黑板（斯坦福同事保留他最后思路的活动黑板）
- **禁忌表达**："这个问题理论上已经有最优解了，不需要再算" "这个模型是对现实的完整描述"

---

## 调研来源

6个调研文件，共约1100行，全部在 [`references/research/`](references/research/) 目录：

| 文件 | 内容 | 行数 |
|------|------|------|
| `01-writings.md` | 著作与论文核心思想（线性规划、分解算法） | 约180行 |
| `02-conversations.md` | 访谈与即兴思考 | 约160行 |
| `03-expression-dna.md` | 表达风格DNA与人格特征 | 约220行 |
| `04-external-views.md` | 他者视角与同行评价 | 约140行 |
| `05-decisions.md` | 重大决策与事后反思 | 约130行 |
| `06-timeline.md` | 人生时间线与学术贡献 | 约110行 |

### 一手来源

Dantzig著作（Linear Programming and Extensions, 1963）· 学术论文（单纯形法、Dantzig-Wolfe分解）· AMS纪念文 · RAND公司档案记录

### 二手来源

同行评价（von Neumann, Koopmans, Gale）· 运筹学史 · 斯坦福大学纪念文献

---

## 这个Skill是怎么造出来的

由 [女娲.skill](https://github.com/Tplovetyx/nuwa-skill) 自动生成。

女娲的工作流程：输入一个名字 → 6个Agent并行调研（著作/对话/表达/批评/决策/时间线）→ 交叉验证提炼心智模型 → 构建SKILL.md → 质量验证（3个已知测试 + 1个边缘测试 + 风格测试）。

想蒸馏其他人？安装女娲：

```bash
npx skills add Tplovetyx/nuwa-skill
```

然后说「蒸馏一个XXX」就行了。

---

## 仓库结构

```
dantzig-perspective/
├── README.md
├── skill.json                           # Skill元信息（触发词、依赖等）
├── SKILL.md                            # 完整思维框架（可直接使用）
├── prompts/                            # 模块化提示词
│   ├── core-mindset.md                # 6个核心心智模型
│   ├── decision-heuristics.md         # 7条决策启发式
│   └── expression-dna.md              # 表达DNA与语言风格
└── references/
    ├── research/                      # 6个调研文件
    │   ├── 01-writings.md
    │   ├── 02-conversations.md
    │   ├── 03-expression-dna.md
    │   ├── 04-external-views.md
    │   ├── 05-decisions.md
    │   └── 06-timeline.md
    └── sources/                       # 原始资料来源
```

---

## 更多.skill

女娲已蒸馏的其他人物，每个都可独立安装：

| 人物 | 领域 | 安装 |
|------|------|------|
| [Karpathy.skill](https://github.com/Tplovetyx/karpathy-skill) | 深度学习/AI工程 | `npx skills add Tplovetyx/karpathy-skill` |
| [芒格.skill](https://github.com/Tplovetyx/munger-skill) | 投资/多元思维 | `npx skills add Tplovetyx/munger-skill` |
| [费曼.skill](https://github.com/Tplovetyx/feynman-skill) | 学习/教学/科学思维 | `npx skills add Tplovetyx/feynman-skill` |
| [姜启源.skill](https://github.com/Tplovetyx/jiang-qiyuan-skill) | 数学建模/问题驱动 | `npx skills add Tplovetyx/jiang-qiyuan-skill` |

想蒸馏更多人？用 [女娲.skill](https://github.com/Tplovetyx/nuwa-skill)，输入任何名字即可。

---

## 许可证

MIT — 随便用，随便改，随便蒸馏。

---

## 关于作者

**花叔 Huashu** — AI Native Coder，独立开发者

| 平台 | 链接 |
|------|------|
| 🌐 官网 | [bookai.top](https://bookai.top) · [huasheng.ai](https://www.huasheng.ai) |
| 𝕏 Twitter | [@AlchainHust](https://x.com/AlchainHust) |

---

*It worked in practice. 这就够了。*

Made with [女娲.skill](https://github.com/Tplovetyx/nuwa-skill)

MIT License © [花叔 Huashu](https://github.com/Tplovetyx)
