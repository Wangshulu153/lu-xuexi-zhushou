# Prior-Art Research: qiaomu-xuexi-zhushou

日期：2026-08-15
创建器：qiaomu-meta-skill（单一创建权威）

## 检索查询

1. `learning assistant skill summarize source into HTML study guide`
2. `study guide skill extract keywords research sources learn topic`
3. `学习助手 技能 提炼关键词 检索资料 生成学习材料`
4. `human-like writing style skill avoid AI flavor Chinese`

数据源：skills.sh（install 计数）、SkillsMP（repo stars）。两个指标语义不同，分开记录，不合并为质量总分。

## 候选与指标

| 候选 | 来源 | 指标 | 进入名单理由 |
|---|---|---|---|
| f-labs-io/agent-html-skills@html-research-reports | skills.sh | 210 installs | HTML 研究报告输出，与“单文件 HTML 学习页”直接相关 |
| petekp/agent-skills@codebase-study-guide | skills.sh | 191 installs | 学习指南类 skill，结构可借鉴 |
| petekp/agent-skills@interactive-study-guide | skills.sh | 41 installs | 交互式学习指南，与自测题机制相关 |
| garethmanning/education-agent-skills@study-strategy-selector | skills.sh | 83 installs | 学习策略选择机制，与“风格自适应”相关 |
| joeseesun/qiaomu-learning@qiaomu-learning | skills.sh | 9 installs | 乔木既有学习 skill，同源风格参考 |
| sickn33/agentic-awesome-skills@humanize-chinese | skills.sh | 596 installs | 中文去 AI 味/人味方向，活人感层参考 |
| sugarforever/01coder-agent-skills@personal-chinese-writing-style | skills.sh | 339 installs | 中文个人写作风格参考 |
| affaan-m/ECC@continuous-learning / continuous-learning-v2 | SkillsMP | repo stars 239888 | 学习体系化与经验提取方向；v1 已弃用 |

SkillsMP 查询日期 2026-08-12（目录更新时间），skills.sh 查询日期 2026-08-15。

## GitHub 源核对状态

2026-08-15 尝试 `skills use` 克隆上述候选仓库（petekp/agent-skills、joeseesun/qiaomu-learning、sickn33/agentic-awesome-skills、sugarforever/01coder-agent-skills、f-labs-io/agent-html-skills）均因 `github.com:443` 连接失败中止。

结论：**remote 候选的源码内容、维护状态、许可证与安全信号无法在本日核对，记为 `missing evidence`**。以下对 remote 候选的机制判断均标记为 hypothesis，不写“已验证”。

## 本地可核对先例

| 技能 | 来源 | 学到的机制 | 落地位置 |
|---|---|---|---|
| content-humanizer | 本地安装 | 把人味拆成可检查维度，用“不编造细节”守住改写边界 | references/huo-ren-gan-mode.md |
| ai-style | 本地安装 | 反 AI 味规则清单化，坏例/好例对照 | references/huo-ren-gan-mode.md |
| structured-prompt-writer | 本地安装 | 输入、输出、角色、流程的结构化表达 | SKILL.md Compact Workflow |

## keep / adapt / reject / invent

### keep

- 学习指南的骨架：学习目标、分章节知识脉络、术语解释、自测题。该结构在多个 study-guide 类候选的名称与描述中一致出现（hypothesis，源码未核对）。
- “先拆解再验证再输出”的工程顺序：本地 content-humanizer 的“分析、改写、复测”循环与本 skill 的“提炼、检索、升华、检查单”一致。

### adapt

- 单文件 HTML 研究报告思路：从 f-labs-io 候选的名称获得启发（hypothesis），适配为“单文件、离线可用、原生 JS 自测题”的中文学习页面，并补来源标注铁律。
- 人味分析/反 AI 味清单：保留其可检查规则与“不改变原意、不编造细节”的边界，去掉量化打分脚本，改为活人感写作层的交付前自查，适配个人学习场景。

### reject

- 爆款文章的战术模式（A/B/C/E）、地缘政治代号、粗口许可：来自用户提供的活人感提示词，服务于病毒式文章而非学习材料，整体舍弃，只保留表达原则。
- affaan-m/ECC 的会话钩子学习系统：面向持续工程学习与技能沉淀，与“把一份资料变成学习材料”的一次性交付不同，舍弃。
- 量化人味打分脚本：个人学习材料不需要稳定评分流水线，输出检查单更轻。

### invent

- 双模式开关：默认“清晰可溯源的教材腔”，只有用户明确要“活人感”时才叠加口语化表达层；事实、结构、来源三个维度不变。
- 关键词提炼 → 资料检索/交叉验证 → 内容升华 → HTML/Markdown 双格式输出的统一知识核心：同一份知识框架可无损导出两种格式，不重复建设两套内容。

## 证据边界

- catalog 指标：有（本报告表格）。
- remote 源码核对：missing evidence（GitHub 网络不可达）。
- 本地源码核对：有（content-humanizer、ai-style、structured-prompt-writer 已读）。
- 输出/运行时/人工评测：缺失；本包只有触发边界评测，输出质量验证依赖后续真实使用。
