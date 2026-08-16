# Creation Handoff: qiaomu-xuexi-zhushou v1.0.0

## Result

- Skill: qiaomu-xuexi-zhushou 1.0.0
- Job: 把任意文本、文件、链接或主题词转化为体系化的 HTML / Markdown 学习材料；只有用户明确要求“活人感”时才叠加自然口吻写作层。
- Local path: D:\Users\AI Workspace\SKILLS\qiaomu-xuexi-zhushou（构建源：D:\Users\AI Workspace\ChatGPT\qiaomu-xuexi-zhushou）
- Publication status: 未发布；仅在本地技能目录使用。

## Reference skills studied

| Skill | 来源与信号 | 学到的机制 | 落地位置 |
|---|---|---|---|
| content-humanizer | 本地安装，已读源码 | 把人味拆成可检查维度，守住“不改变原意、不编造细节”的改写边界 | references/huo-ren-gan-mode.md |
| ai-style | 本地安装，已读源码 | 反 AI 味规则清单化，坏例/好例对照 | references/huo-ren-gan-mode.md |
| structured-prompt-writer | 本地安装，已读源码 | 输入、输出、角色、流程的结构化表达 | SKILL.md Compact Workflow |
| petekp/agent-skills@codebase-study-guide | skills.sh，191 installs（2026-08-15） | 学习指南骨架（学习目标、章节、自测） | references/learning-workflow.md；源码未核对，标为 hypothesis |
| petekp/agent-skills@interactive-study-guide | skills.sh，41 installs（2026-08-15） | 交互式学习机制 | references/learning-workflow.md；源码未核对，标为 hypothesis |
| f-labs-io/agent-html-skills@html-research-reports | skills.sh，210 installs（2026-08-15） | 单文件 HTML 报告输出思路 | references/output-checklist.md；源码未核对，标为 hypothesis |
| sickn33/agentic-awesome-skills@humanize-chinese | skills.sh，596 installs（2026-08-15） | 中文去 AI 味方向 | references/huo-ren-gan-mode.md；源码未核对，标为 hypothesis |
| sugarforever/01coder-agent-skills@personal-chinese-writing-style | skills.sh，339 installs（2026-08-15） | 中文个人写作风格方向 | references/huo-ren-gan-mode.md；源码未核对，标为 hypothesis |
| affaan-m/ECC@continuous-learning-v2 | SkillsMP，repo stars 239888（目录更新 2026-08-12） | 学习体系化方向 | 研究记录于 reports/prior-art-research.md |

## Absorbed and rejected

- keep：学习指南骨架；先拆解、再验证、后输出的工程顺序。
- adapt：单文件 HTML 研究报告思路适配为离线中文学习页；人味分析/反 AI 味清单去掉量化打分，改为写作层自查单。
- reject：爆款文章的战术模式、地缘政治代号、粗口许可；会话钩子式持续学习系统；量化人味打分流水线。
- invent：默认“清晰教材腔”与按需“活人感”双模式开关；关键词提炼 → 检索交叉验证 → 内容升华 → HTML/Markdown 双格式输出的统一知识核心。

## Advantages and highlights

| Label | 说明 |
|---|---|
| design advantage | 本包把“活人感”做成显式开关：默认不改变教学口吻，只有用户点名要求时才叠加表达层，避免把学习材料写成文章腔。 |
| design advantage | 同一份知识框架支持 HTML 与 Markdown 双输出，HTML 单文件、离线、原生 JS 自测题，Markdown 结构化笔记，内容不重复建设。 |
| validated advantage | 触发边界评测 18/18 通过（8 个应触发、6 个不应触发、4 个近邻场景）。 |
| hypothesis | 期望远程候选中的“学习指南骨架”与“单文件 HTML 报告”思路有效，但 GitHub 源核对失败，属 missing evidence，待网络恢复后复核。 |

## Verification and limits

- validate_skill.py：通过（Production 必需证据齐全，0 failures，0 warnings）。
- trigger_eval.py：18/18 通过，pass_rate 1.0。
- export_skill_ir.py：已生成 reports/skill-ir.json。
- missing evidence：remote 候选源码核对（GitHub 连接失败）；输出质量与运行时行为的人工/真实使用评测。
- 权限边界：本包只读取用户提供的资料并生成 HTML/Markdown 输出文件；不发布、不执行第三方脚本、不调用账号服务。
