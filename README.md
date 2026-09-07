# agent-skills

个人 Agent Skills 集合（适用于支持 Agent Skills 的环境：Claude Code、Claude.ai 等）。

## 包含技能

| 技能 | 说明 |
|------|------|
| `decision-challenge` |
| `dev-mentor` | **引导式开发**：AI 只辅助、不代写。任务拆解 + 逐个引导 + 五维标准代码审查（正确性/可读性/健壮性/规范性/扩展性），严格批评、不奉承，帮用户亲手写出代码并积累经验 | **反谄媚决策质询**：重要决策时用三阶段对抗质询（最强反方 → 最强正方 → 中立裁判），对抗 LLM 的谄媚倾向（sycophancy），输出不迎合的诚实分析 |

## 安装

以 Claude Code 为例，把技能目录复制到 skills 目录：

```bash
# 个人级（所有项目可用）
mkdir -p ~/.claude/skills
cp -r skills/decision-challenge ~/.claude/skills/

# 或项目级（仅当前项目，随 git 共享给团队）
mkdir -p .claude/skills
cp -r skills/decision-challenge .claude/skills/
```

## 使用

安装后直接描述一个你**倾向做出的决定**即可自动触发，例如：

> 我倾向买 HD490 Pro 而不是 HD660S2 来听 ACG，因为……

技能会输出三阶段分析：

1. **反方质询**——最强立场证明你可能是错的（遗漏事实 / 过度乐观假设 / 不可逆成本 / 认知偏差）
2. **正方辩护**——这个决定真正成立的最强理由（钢人论证）
3. **中立裁判**——哪方更强 + 最大未知变量 + 什么新信息会让结论反转（不和稀泥、不五五开）

## 目录规范

```
skills/<skill-name>/
├── SKILL.md                 # 技能主文件（frontmatter 的 description 决定触发）
└── references/              # 渐进式披露：完整示例等，按需加载
```

## License

MIT © 2026 Arletaa

