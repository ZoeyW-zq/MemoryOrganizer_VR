# Memory Organizer Portfolio Case Study

## Positioning

This case should present Zoey as an **XR interaction developer and experience designer** who can connect narrative intent to reliable Unity systems. The strongest evidence is not the number of features, but the complete relationship between spatial interaction, authored pacing, embodied transitions, audio, and outcome feedback.

Recommended project order on the current portfolio: **second**, after the Typewriter project. It is the strongest evidence of end-to-end narrative systems work; the Stroke Rehabilitation project can follow as evidence of research and user testing.

## Card

**English title**  
Memory Organizer: A VR Narrative Experience

**Chinese title**  
记忆整理师：VR 叙事体验

**English subtitle**  
A VR interaction system built around memory sorting, state flow, and AI voice timing

**Chinese subtitle**  
一个围绕记忆分类、状态流程与 AI 语音节奏的 VR 交互系统

**Card tags**  
Unity · C# · XR Interaction Toolkit · Narrative Design

Do not use `Convai` as a primary card tag. It was a comparative prototype rather than the final interaction direction. Include it in the case study where the decision can be explained honestly.

## Project Metadata

| Field | Value |
|---|---|
| Platform | Meta Quest VR · WebGL |
| Engine | Unity 6 |
| SDK | XR Interaction Toolkit · OpenXR |
| Role | XR Interaction Development · Experience Design · Narrative Systems |
| Development | June-September 2026 |
| AI experiment | Convai 4.5.0 prototype · pre-generated AI TTS in final version |
| Repository | https://github.com/ZoeyW-zq/9903_Zoey |

If this was a team project, replace the Role row with the exact division of work before publishing. Do not label it a solo project unless that is accurate.

## Overview

### English

How can an abstract idea become a clear VR interaction system?

Memory Organizer is a five-stage VR experience built around a simple spatial rule: seven memory objects are sorted into Focus, Context, or Background. The project uses that rule to organise interaction, content flow, and final feedback. Instead of long exposition, the experience relies on placement, state changes, branching responses, and outcome composition to communicate meaning.

I designed the interaction flow and implemented the Unity systems that support it: XR object interaction, state-driven scene transitions, branching dialogue, spatial audio, character IK, comfort-aware player movement, and a compositional outcome system.

### 中文

如何把一个抽象概念转化为清晰的 VR 交互系统？

《记忆整理师》是一段以空间规则为核心的五阶段 VR 体验。玩家需要将七件记忆物品分别放入“聚焦”“语境”或“背景”。项目用这一套规则组织交互、内容节奏和最终反馈。体验不依赖大量叙事说明，而是通过放置、状态切换、分支回应和结果组合来传达含义。

我负责设计交互流程，并实现支撑整个体验的 Unity 系统，包括 XR 物体交互、状态驱动的场景切换、分支对话、空间音频、角色 IK、兼顾舒适度的玩家移动，以及组合式结果生成。

## Case Study Block 1

### English title

Memory as interaction

### English copy

The central mechanic turns an abstract idea into a physical sorting task. Memories are not labelled good or bad, and the player cannot erase them. Instead, each object is placed in Focus, Context, or Background to express how much attention it should receive now.

Three surface memories establish the rule set, then four deeper items unlock through branching responses. The player can approach the four conversations in any order, and each one advances through content states instead of a simple pass/fail loop. This keeps the structure readable while still giving the player ownership over the sequence.

When all seven objects return to the memory room, the final redistribution turns interpretation into a visible outcome. The project uses that final placement as feedback, not as a score.

### 中文标题

记忆作为交互

### 中文文案

核心机制把抽象概念转化为一个可操作的空间分类任务。记忆不被简单标记为好或坏，玩家也不能删除它们；玩家要做的是把每件物品放入“聚焦”“语境”或“背景”，表达它在当下应该获得多少注意力。

体验先用三段表层内容建立规则，再让四段深层内容通过分支回应逐步解锁。四组内容可以按任意顺序完成，每一组都通过状态推进而不是单纯的对错判断来延展流程。这样结构清楚，但玩家仍然有顺序选择的自由。

玩家带着全部七件物品回到记忆空间后，可以在确认前反复调整分配。这里的能动性来自理解和取舍，而不是输赢。

**Recommended media**: one 8-12 second clip of placing memories across the three zones; one 8-12 second clip showing a mirror conversation followed by the mirror shattering.

## Case Study Block 2

### English title

State-driven flow

### English copy

A central C# state machine coordinates the five-stage flow across three scene roots, keeping only the current environment active. It synchronises dialogue availability, object states, fades, post-processing, particles, spatial audio, player placement, and the final report while preserving progress when the player leaves and later returns to the memory room.

The transition sequence combines IK, fade timing, and player-follow logic so a dramatic scene shift can happen without forcing headset rotation or breaking comfort rules.

The ending uses a compositional report rather than hundreds of hard-coded branches. Seven memories across three attention zones allow 3^7, or 2,187, possible layouts. I authored 21 object-and-position outcome fragments, then assembled the seven relevant findings at runtime. The result stays specific to the player's choices without treating any distribution as a score.

### 中文标题

状态驱动的流程

### 中文文案

中央 C# 状态机负责协调五个阶段与三个场景根节点，并确保只有当前环境保持激活。它统一管理对话可用状态、物体状态、屏幕淡入淡出、后期效果、粒子、空间音频、玩家位置与最终报告；玩家离开并返回记忆空间时，之前的放置结果也会被保留。

危机段落把 IK、淡出时机与玩家跟随逻辑组合成一次连续的场景转换，在不强制旋转视角的前提下完成强烈的空间切换。

结局没有为每一种组合硬编码一份报告。七段记忆分别对应三个注意力层级，共产生 3^7，也就是 2,187 种可能布局。我为每件物品编写三个位置结果，总计 21 条内容，再由系统在运行时组合出与本次选择对应的七条反馈。结果保持具体，但不会把任何分配方式定义成分数或标准答案。

**Recommended media**: one 10-15 second crisis clip from roof grab to swallow fade; one still or short clip of the final report; optionally a simple five-stage flow diagram.

## Case Study Block 3

### English title

AI voice prototype

### English copy

I built an isolated Convai prototype to test whether a generative AI companion could replace the scripted assistant. Convai was connected through push-to-talk, Narrative Design sections, dynamic scene context, and a validation bridge that kept Unity as the sole authority over physical progression. The integration worked as a technical proof: the character could respond to natural-language intent while remaining aware of the current stage.

It did not improve the finished experience. Response timing and generated delivery were less predictable, which weakened transitions and interrupted the planned interaction rhythm. The standard assistant uses authored dialogue with pre-generated AI text-to-speech clips. That approach gives direct control over wording, intonation, duration, interruption rules, and exactly when each line releases the next event. It produced clearer pacing and stronger atmosphere.

The Convai version remains a useful comparative prototype, not a discarded failure. It established a practical boundary: generative conversation is valuable where player questions are genuinely open-ended, but authored voice is the better tool when pacing and event synchronisation carry the experience.

### 中文标题

AI 语音原型

### 中文文案

我在独立场景中接入 Convai，测试生成式 AI 伙伴能否替代原有的脚本型助手。该原型采用按键说话、Narrative Design 分段、动态场景上下文，并通过本地验证桥接保证 Unity 始终拥有物理流程的唯一控制权。作为技术验证，它能够理解自然语言意图，并根据玩家所在阶段给出回应。

但它没有让最终体验变得更好。远程响应时间和生成式表达都更难预测，容易削弱转场节奏、打断计划好的交互节拍。普通版助手采用预先编写的内容与 AI 生成的 Text-to-Speech 音频，因此我可以精确控制台词、语调、时长、中断规则，以及每句话在什么时刻释放下一个事件。它最终带来了更清晰的节奏和更稳定的氛围。

因此，Convai 版本被保留为一个有价值的对照原型，而不是被掩盖的失败。这个实验帮我明确了技术边界：当玩家的问题真正开放时，生成式对话很有价值；当体验依赖节奏与事件同步时，经过编排的语音仍然更合适。

**Recommended media**: a concise 12-20 second A/B comparison. Show the same narrative beat in the Convai prototype and the authored-TTS version. Add visible labels and subtitles; do not publish a long raw recording of latency.

## Suggested Detail-Page Information Rows

| Label | Value |
|---|---|
| Platform | Meta Quest VR · WebGL |
| Engine | Unity 6 · XR Interaction Toolkit · OpenXR |
| Systems | State machine · branching dialogue · IK sequence · spatial audio · compositional report |
| Narrative scope | 5 stages · 7 memories · 4 mirror conversations · 2,187 possible final layouts |
| AI prototype | Convai 4.5.0 · push-to-talk · Narrative Design · dynamic context |
| GitHub | github.com/ZoeyW-zq/9903_Zoey |

## Media Placement

Use the assets in this order on the portfolio page:

1. Card cover video: `video/Memory_coverVideo.mp4`
2. Detail-page hero image: `images/memory_hero.jpeg`
3. Block 1 media row: `video/Memory_placement.mp4` and `video/Memory_mirror.mp4`
4. Block 2 media row: `video/Memory_clown.mp4` and `images/memory_report.jpeg`
5. Block 3 media row: `video/Memory_convai_ab.mp4`

If you only have time to prepare three assets first, make these:

- `images/memory_hero.jpeg`
- `video/Memory_placement.mp4`
- `images/memory_report.jpeg`

## Asset Brief

### Required

1. **Card cover video**: 6-10 seconds, seamless loop, 16:9 master. Use a clean sequence with the player placing a memory, the room reacting, and a brief glimpse of the Giant Clown. It must still read when muted and cropped to 3:2.
2. **Hero image**: 2200 x 950 px or larger, composed for a 21:9 crop. Best option: the player-facing view of the memory room with the three attention zones and several distinctive memory objects visible. Keep key content in the centre 60%.
3. **Core mechanic clip**: 8-12 seconds showing a memory object being inspected and moved between Focus, Context, and Background.
4. **Mirror conversation clip**: 8-12 seconds showing a choice, environmental response, and successful mirror shatter. Include subtitles because the meaning matters.
5. **Crisis clip**: 10-15 seconds from the Giant Clown opening the roof through the black swallow transition. Use the stable take with no editor UI, Guardian boundary, or debug text.
6. **Outcome image or clip**: a readable capture of the final report, ideally preceded by a brief shot of all seven objects in their final zones.
7. **Convai comparison**: two short captures of the same Office or Memory Room beat, one from Convai and one from the authored-TTS version. Preserve the voice audio and add matching subtitles.

### Optional but valuable

1. A clean top-down or wide shot of all seven memory objects.
2. A Unity editor capture of the three major scene roots and the central state controller. Use only one technical screenshot; the page should stay experience-led.
3. A simple diagram of the five-stage journey: Office -> Memory Room -> Giant Crisis -> Mirror Chamber -> Final Redistribution and Report.
4. A 45-60 second case-study reel combining interaction, crisis, mirror dialogue, final placement, and outcome. This should supplement the page, not replace the shorter clips.

### Capture specification

- Record at 1920 x 1080 or higher, 30 or 60 fps, H.264 MP4.
- Keep important action inside the centre safe area so the same source survives 3:2 and 21:9 crops.
- Use slow, intentional head movement. Avoid rapid headset turns and controller jitter.
- Capture clean game output with no Unity editor chrome, performance overlay, Guardian boundary, debug logs, or personal/account information.
- Preserve spatial SFX and assistant voice for detail clips. The card cover should also communicate clearly while muted.
- Capture the authored-TTS version as the primary experience. Label Convai footage explicitly as `AI NPC Prototype` so viewers do not mistake it for the final direction.

## Editing Notes

- Keep the Overview and three blocks; do not add a long feature list. The current portfolio works best when each case has a clear design question, a technical response, and an honest conclusion.
- Lead with the spatial memory mechanic, not with the Giant Clown. The clown is a strong visual hook, but without the mechanic it can make the project look like a horror demo rather than an interaction-design case study.
- Keep the `2,187 possible layouts / 21 authored fragments` detail. It is compact evidence of systems thinking and content-aware implementation.
- Keep the Convai comparison. The strongest hiring signal is the evaluation and product decision, not simply that an SDK was connected.
- Do not claim psychological or therapeutic efficacy. This is a narrative metaphor and interaction design project, not a clinical intervention.
- Do not publish Convai credentials, dashboard identifiers, raw service logs, or backend screenshots containing account information.
