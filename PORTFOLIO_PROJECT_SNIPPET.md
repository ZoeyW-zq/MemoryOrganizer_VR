# Portfolio Project Snippet

Use this snippet for the live portfolio at `https://zoeysportfolio.edgeone.app/`.

Recommended placement: insert this object after the Typewriter project. Then update the later project numbers:

- Stroke Rehabilitation: `03`
- Temple Ruins: `04`
- WebXR Mini-Game: `05`

## Suggested Asset Names

Place these files in the same asset folders used by the current portfolio:

- `images/memory_hero.jpeg`
- `images/memory_report.jpeg`
- `video/Memory_coverVideo.mp4`
- `video/Memory_placement.mp4`
- `video/Memory_mirror.mp4`
- `video/Memory_clown.mp4`
- `video/Memory_convai_ab.mp4`

## Media Mapping

Use the assets in this order on the detail page:

- Card cover: `video/Memory_coverVideo.mp4`
- Hero image: `images/memory_hero.jpeg`
- Block 1: `video/Memory_placement.mp4` + `video/Memory_mirror.mp4`
- Block 2: `video/Memory_clown.mp4` + `images/memory_report.jpeg`
- Block 3: `video/Memory_convai_ab.mp4`

If you only prepare three assets first, prioritize:

- `images/memory_hero.jpeg`
- `video/Memory_placement.mp4`
- `images/memory_report.jpeg`

## PROJECTS Object

```js
{
  num: "02",
  title: "Memory Organizer: A VR Narrative Experience",
  titleZh: "记忆整理师：VR 叙事体验",
  tags: ["Unity", "C#", "XR Interaction Toolkit"],
  stack: [
    "Unity 6",
    "C#",
    "XR Interaction Toolkit",
    "OpenXR",
    "Convai Prototype",
    "AI Text-to-Speech",
  ],
  sub: "A VR interaction system about memory sorting, state flow, and AI voice timing",
  accent: "#8a4fd8",
  img: "images/memory_hero.jpeg",
  video: "video/Memory_coverVideo.mp4",
  overview:
    "<p>How can an abstract idea become a clear VR interaction system?</p><p>Memory Organizer is a five-stage VR experience built around a simple spatial rule: seven memory objects are sorted into Focus, Context, or Background. The project uses that rule to organise interaction, content flow, and final feedback. Instead of long exposition, the experience relies on placement, state changes, branching responses, and outcome composition to communicate meaning.</p><p>I designed the interaction flow and implemented the Unity systems that support it: XR object interaction, state-driven scene transitions, branching dialogue, spatial audio, character IK, comfort-aware player movement, and a compositional outcome system.</p>",
  overviewZh:
    "<p>如何把一个抽象概念转化为清晰的 VR 交互系统？</p><p>《记忆整理师》是一段以空间规则为核心的五阶段 VR 体验。玩家需要将七件记忆物品分别放入“聚焦”“语境”或“背景”。项目用这一套规则组织交互、内容节奏和最终反馈。体验不依赖大量叙事说明，而是通过放置、状态切换、分支回应和结果组合来传达含义。</p><p>我负责设计交互流程，并实现支撑整个体验的 Unity 系统，包括 XR 物体交互、状态驱动的场景切换、分支对话、空间音频、角色 IK、兼顾舒适度的玩家移动，以及组合式结果生成。</p>",
  blocks: [
    {
      title: "Memory as interaction",
      text: "<p>The central mechanic turns an abstract idea into a physical sorting task. Memories are not labelled good or bad, and the player cannot erase them. Instead, each object is placed in Focus, Context, or Background to express how much attention it should receive now.</p><p>Three surface memories establish the rule set, then four deeper items unlock through branching responses. The player can approach the four conversations in any order, and each one advances through content states instead of a simple pass/fail loop. This keeps the structure readable while still giving the player ownership over the sequence.</p><p>When all seven objects return to the memory room, the final redistribution turns interpretation into a visible outcome. The project uses that final placement as feedback, not as a score.</p>",
      imgs: ["video/Memory_placement.mp4", "video/Memory_mirror.mp4"],
      videoMode: "hover",
      cols: 2,
    },
    {
      title: "State-driven flow",
      text: "<p>A central C# state machine coordinates the five-stage flow across three scene roots, keeping only the current environment active. It synchronises dialogue availability, object states, fades, post-processing, particles, spatial audio, player placement, and the final report while preserving progress when the player leaves and later returns to the memory room.</p><p>The transition sequence combines IK, fade timing, and player-follow logic so a dramatic scene shift can happen without forcing headset rotation or breaking comfort rules.</p><p>The ending uses a compositional report rather than hundreds of hard-coded branches. Seven memories across three attention zones allow 3^7, or 2,187, possible layouts. I authored 21 object-and-position outcome fragments, then assembled the seven relevant findings at runtime. The result stays specific to the player's choices without treating any distribution as a score.</p>",
      imgs: ["video/Memory_clown.mp4", "images/memory_report.jpeg"],
      cols: 1,
      landscape: true,
    },
    {
      title: "AI voice prototype",
      text: "<p>I built an isolated Convai prototype to test whether a generative AI companion could replace the scripted assistant. Convai was connected through push-to-talk, Narrative Design sections, dynamic scene context, and a validation bridge that kept Unity as the sole authority over physical progression. The integration worked as a technical proof: the character could respond to natural-language intent while remaining aware of the current stage.</p><p>It did not improve the finished experience. Response timing and generated delivery were less predictable, which weakened transitions and interrupted the planned interaction rhythm. The standard assistant uses authored dialogue with pre-generated AI text-to-speech clips. That approach gives direct control over wording, intonation, duration, interruption rules, and exactly when each line releases the next event. It produced clearer pacing and stronger atmosphere.</p><p>The Convai version remains a useful comparative prototype, not a discarded failure. It established a practical boundary: generative conversation is valuable where player questions are genuinely open-ended, but authored voice is the better tool when pacing and event synchronisation carry the experience.</p>",
      imgs: ["video/Memory_convai_ab.mp4"],
      cols: 1,
      landscape: true,
    },
  ],
  blocksZh: [
    {
      title: "记忆作为交互",
      text: "<p>核心机制把抽象概念转化为一个可操作的空间分类任务。记忆不被简单标记为好或坏，玩家也不能删除它们；玩家要做的是把每件物品放入“聚焦”“语境”或“背景”，表达它在当下应该获得多少注意力。</p><p>体验先用三段表层内容建立规则，再让四段深层内容通过分支回应逐步解锁。四组内容可以按任意顺序完成，每一组都通过状态推进而不是单纯的对错判断来延展流程。这样结构清楚，但玩家仍然有顺序选择的自由。</p><p>玩家带着全部七件物品回到记忆空间后，可以在确认前反复调整分配。这里的能动性来自理解和取舍，而不是输赢。</p>",
    },
    {
      title: "状态驱动的流程",
      text: "<p>中央 C# 状态机负责协调五个阶段与三个场景根节点，并确保只有当前环境保持激活。它统一管理对话可用状态、物体状态、屏幕淡入淡出、后期效果、粒子、空间音频、玩家位置与最终报告；玩家离开并返回记忆空间时，之前的放置结果也会被保留。</p><p>危机段落把 IK、淡出时机与玩家跟随逻辑组合成一次连续的场景转换，在不强制旋转视角的前提下完成强烈的空间切换。</p><p>结局没有为每一种组合硬编码一份报告。七段记忆分别对应三个注意力层级，共产生 3^7，也就是 2,187 种可能布局。我为每件物品编写三个位置结果，总计 21 条内容，再由系统在运行时组合出与本次选择对应的七条反馈。结果保持具体，但不会把任何分配方式定义成分数或标准答案。</p>",
    },
    {
      title: "AI voice prototype",
      text: "<p>I built an isolated Convai prototype to test whether a generative AI companion could replace the scripted assistant. Convai was connected through push-to-talk, Narrative Design sections, dynamic scene context, and a validation bridge that kept Unity as the sole authority over physical progression. The integration worked as a technical proof: the character could respond to natural-language intent while remaining aware of the current stage.</p><p>It did not improve the finished experience. Response timing and generated delivery were less predictable, which weakened transitions and interrupted the planned interaction rhythm. The standard assistant uses authored dialogue with pre-generated AI text-to-speech clips. That approach gives direct control over wording, intonation, duration, interruption rules, and exactly when each line releases the next event. It produced clearer pacing and stronger atmosphere.</p><p>The Convai version remains a useful comparative prototype, not a discarded failure. It established a practical boundary: generative conversation is valuable where player questions are genuinely open-ended, but authored voice is the better tool when pacing and event synchronisation carry the experience.</p>",
    },
  ],
  info: [
    ["Platform", "Meta Quest VR · WebGL"],
    ["Engine", "Unity 6 · XR Interaction Toolkit · OpenXR"],
    ["Systems", "State machine · branching dialogue · IK sequence · spatial audio · compositional report"],
    ["Narrative scope", "5 stages · 7 memories · 4 mirror conversations · 2,187 possible final layouts"],
    ["AI prototype", "Convai 4.5.0 · push-to-talk · Narrative Design · dynamic context"],
    [
      "GitHub",
      '<a href="https://github.com/ZoeyW-zq/9903_Zoey" target="_blank" rel="noopener noreferrer">github.com/ZoeyW-zq/9903_Zoey</a>',
    ],
  ],
  metaCols: [
    { label: "Platform", value: "Meta Quest VR · WebGL" },
    { label: "Engine", value: "Unity 6" },
    { label: "Systems", value: "Narrative systems · XR interaction · AI prototype" },
  ],
}
```

## Publishing Notes

- Keep the card tags focused on the final work: `Unity`, `C#`, and `XR Interaction Toolkit`.
- Keep Convai inside the case study body and info table, not as a main card tag.
- Use the authored Text-to-Speech version as the primary footage.
- Label the Convai comparison clip clearly as `AI NPC Prototype`.
- Avoid claiming therapeutic effect. Present the memory system as narrative metaphor and interaction design.
