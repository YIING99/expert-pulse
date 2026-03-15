# Expert Pulse (把脉) — Cross-Disciplinary Decision Review for Claude Code

> When AI presents options A/B/C, you're anchored to that option space. Expert Pulse runs a second pass through 3-5 cross-disciplinary lenses and often surfaces a superior Option D.

## What It Does

Expert Pulse is a Claude Code skill that transforms routine "pick A or B" moments into structured expert reviews. It selects relevant expert perspectives (cognitive psychology, behavioral economics, platform design, etc.), analyzes the decision through each lens, and delivers a synthesized recommendation with an evaluation framework.

**Two trigger modes:**
- **Automatic** — When Claude is about to present multiple options for a major product decision, it enters expert review mode instead of just asking you to pick
- **Manual** — Say **"把脉"** (Chinese for "take the pulse") anywhere in your message to trigger an expert review on the current topic

## Example

You're designing a "Soul" (user profile) feature and discussing data source architecture. Instead of getting "here are 3 options, which do you prefer?", Expert Pulse kicks in:

```
专家视角选择：认知心理学（约哈里窗）、平台设计（双边数据网络效应）、
行为设计（Fogg 行为模型）、隐私架构（Privacy by Design）、
标杆产品参考（Spotify Wrapped 的数据叙事）

推荐方案：选 B（双源加权）但增加一层 — 不只是静态加权，
而是让用户看到 Soul 是如何被"两种声音"塑造的...

评估框架：
| 标准 | 说明 |
|------|------|
| 数据丰富度 | Soul 画像是否能在早期就有足够信号？ |
| 用户感知 | 用户觉得 Soul "懂我"而不是"监视我"？ |
| 冷启动 | 新用户没有 AI 记忆时 Soul 是否仍有价值？ |
| 实现复杂度 | 加权逻辑是否可以在当前架构下 2 周内上线？ |
```

## Install

```bash
# Copy to your Claude Code skills directory
cp -r expert-pulse ~/.claude/skills/

# Or clone this repo
git clone https://github.com/YIING99/expert-pulse.git ~/.claude/skills/expert-pulse
```

Restart Claude Code. The skill activates automatically on major product decisions, or manually when you say "把脉".

## When It Triggers

**Auto-triggers on:**
- Product positioning or competitive strategy
- User experience models or interaction paradigms
- Data architecture with user-facing implications
- Pricing or monetization strategy
- Feature prioritization or roadmap direction
- Onboarding or activation flow design
- API/protocol design decisions

**Does NOT trigger on:** implementation-level choices (library selection, variable naming, minor refactors), bug fixes, or decisions where you've already expressed a clear preference.

## Execution Flow

1. **Present the Landscape** — List options with brief pros/cons (skipped in manual mode)
2. **Select Expert Lenses** — 3-5 cross-disciplinary perspectives based on decision type
3. **Expert Analysis** — Each lens challenges assumptions and surfaces missed trade-offs
4. **Synthesized Recommendation** — One clear path + quick evaluation framework
5. **Save Decision** — After you choose, optionally saves to KnowMine knowledge base

## Expert Lens Library

| Decision Domain | Candidate Expert Lenses |
|---|---|
| UX / Interaction | Cognitive psychology, behavioral economics, accessibility, game design |
| Product Positioning | Jobs-to-be-done, blue ocean strategy, platform economics |
| Pricing | Behavioral economics, SaaS metrics, price psychology |
| Data Architecture | Systems thinking, domain-driven design, privacy-by-design |
| Onboarding | Motivation theory (Fogg, SDT), progressive disclosure, habit formation |
| API Design | Developer experience, network effects, composability principles |

## Requirements

- Claude Code (any version with skills support)
- Optional: [KnowMine](https://knowmine.ai) MCP for auto-saving decisions

## License

MIT

---

Built by [KING](https://github.com/YIING99)
