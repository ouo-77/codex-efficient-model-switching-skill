# 贪吃蛇探索实验 / Exploratory Snake Comparison
日期 / Date: 2026-11-13

补充材料 / Supplement: [脱敏聊天摘录 / redacted excerpts](transcript.redacted.md) · [结构化计数和父会话边界 / usage counters and parent boundaries](usage.json)

## 设置 / Setup
旧版 Skill 在已有长对话中由 Astra 规划、协调，Luna 实现。对照组使用独立 Astra 执行者，不启用 Skill、不读旧游戏，生成另一份离线贪吃蛇。两组都要求键盘/触屏控制、暂停重开、分数和最高分、食物增长及碰撞结束。
The old workflow used Astra coordination in a long conversation and a Luna worker. The comparator used a fresh Astra worker without the skill or the existing game, with the same feature brief.

| 运行 / Run | 输入 / Input | 缓存输入（包含于输入） / Cached input (subset) | 输出 / Output | 总量 / Total |
|---|---:|---:|---:|---:|
| Old skill: Astra parent | 1,735,636 | 1,722,752 | 1,055 | 1,736,691 |
| Old skill: Luna worker | 128,228 | 98,048 | 2,967 | 131,195 |
| Old skill combined | 1,863,864 | 1,820,800 | 4,022 | 1,867,886 |
| No skill: fresh Astra worker | 67,386 | 43,776 | 2,146 | 69,532 |

来源：本机 Codex 会话日志的累计 token 计数差（父会话）及独立执行者最终计数。原始日志不公开。父会话数据包含规划、工具观察、等待后的后续交互和收尾，不是纯规划开销。
Source: local Codex cumulative usage deltas for the parent and final worker counters. Raw logs are not published. Parent usage includes planning, observations, follow-up interaction and wrap-up, not planning alone.

## 验证 / Verification
Luna 版做过代码检查及独立 Edge 启动/撞墙冒烟；浏览器自动化受占用影响，未实测手机触控。对照版以本地限步脚本测试吃食、增长、分数、转向、暂停、重开及两类碰撞；未验证实际触屏手势和视觉布局。
The Luna version had code inspection and an Edge startup/wall-collision smoke test, without mobile touch verification. The comparator passed bounded script tests for growth, scoring, turning, pause, restart and collisions, without real touch or visual-layout checks.

## 不能得出的结论 / What this does not establish
- 不是受控 A/B：长历史与新会话、不同宿主/模型、缓存命中及测试覆盖不同。不能将差值归因于 Skill，也不能推断新版节省率。
- 未缓存输入加输出分别为 47,086 与 25,756，仅为描述性统计，不是 Plus 扣额。
- 一个中止的 CLI 对照尝试缺少完整用量，未纳入表内；本次实验研究/修改 Skill 的开销也不在表内。这不是整个研究活动的完整成本。
- 未测 Plus 实扣、API 账单或所有模型的最低消费；未做重复试验。

This is not a controlled A/B: context length, host/model, cache and test coverage differ. The differences cannot be attributed to the skill or used to predict savings for the new revision. Noncached input plus output was 47,086 versus 25,756, not a Plus billing calculation. An aborted CLI attempt lacked complete usage and is excluded, as is research/skill-editing overhead. No Plus deductions, API bills, global minimum cost or repeated trials were measured.

## 下一轮 / Next study
固定模型版本、上下文、起点、验收脚本及宿主，分别测直接执行与 Astra 规划交接，重复多次并记录失败/重试；仅在用户要求时额外花额度做实验。
Hold model versions, context, starting files, acceptance tests and host constant; compare direct execution with planned handoff across repeated trials, including failures/retries. Run additional paid/quota-consuming trials only on request.
