# qiaomu-xuexi-zhushou

> 把任意文本、文件、链接或主题词变成体系化的 HTML / Markdown 学习材料；只有你说“要活人感”时才切换自然口吻写作层。

## 它解决什么问题

用户丢给 AI 一段笔记、一篇链接或一个主题词，通常想要的不是一句解释，而是一份能真正学进去的材料。这个 skill 稳定接住整条链路：提炼关键词、检索并交叉验证资料、升华成知识框架、最后按用户选择输出可离线使用的 HTML 学习页面或 Markdown 学习笔记。

## 安装

```bash
npx skills add joeseesun/qiaomu-xuexi-zhushou
```

本地使用：把 `qiaomu-xuexi-zhushou` 目录放进你的 skills 目录即可。

## 你可以直接这样说

- “帮我学习这篇文章，提炼关键词，检索相关资料，输出成 HTML 学习页面。”
- “把这份笔记做成 markdown 学习资料，先总结要点再查找相关资料。”
- “学一下宋朝经济，做成 markdown 学习笔记，要像人写的自然一点。”
- “用活人感帮我学习这个主题，输出成 HTML 学习材料。”

## 输出

- HTML：单文件、响应式、无外部依赖；封面、目录、章节、术语卡、原生 JS 自测题、来源引用区。
- Markdown：结构化标题、学习目标、关键词表、术语表、自测题答案与解析、来源列表。
- 两者都保持来源可溯，未验证的模型固有知识明确标注。

## 活人感模式

默认教学口吻清晰准确；只有当用户明确说“活人感”“像人写的”“别太 AI”时才叠加写作层：隐喻讲清概念、术语降维、用“微信聊天测试”检查句子、拒绝金句腔。事实、结构、来源不变。

## 验证

```bash
python D:\Users\AI Workspace\SKILLS\qiaomu-meta-skill\scripts\validate_skill.py .
python D:\Users\AI Workspace\SKILLS\qiaomu-meta-skill\scripts\trigger_eval.py . --cases evals/trigger_cases.json --output reports/trigger-eval.json
python D:\Users\AI Workspace\SKILLS\qiaomu-meta-skill\scripts\export_skill_ir.py . --output reports/skill-ir.json
```

## Troubleshooting

| 问题 | 常见原因 | 处理方式 |
|---|---|---|
| 页面内容像占位符 | 跳过了检索或照抄框架 | 按 references/learning-workflow.md 走完整流程并运行交付前检查单 |
| 用户没说要“活人感”却写得很随意 | 误开写作层 | 默认关闭活人感层，只在用户明确要求时启用 |
| 来源可疑或无法验证 | 联网工具不可用 | 先声明“当前环境无法联网检索”，征得用户同意后再基于模型固有知识降级 |
| 触发过宽或过窄 | description 与真实说法不匹配 | 补 should-trigger / should-not-trigger 用例后重跑 trigger_eval.py |

## 致谢与来源

- 学习工作流语义改编自用户的《AI学习助手SP.md》。
- 活人感写作层语义改编自 添锦 & Prometheus 的开源《爆款文章创作引擎 v18 - 反金句版》，仅取表达原则，不取爆款文章的战术模式。
- 先例研究见 reports/prior-art-research.md。

Upstream inspiration: G:/学习提升/AI学习/AI Agent/My Prompt/AI学习助手SP.md; G:/学习提升/AI学习/AI Agent/System Prompt/活人感提示词（开源）Gemini.md

Copyright (c) 向阳乔木 | X: https://x.com/vista8 | GitHub: https://github.com/joeseesun/
