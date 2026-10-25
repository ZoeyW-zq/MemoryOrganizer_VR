# Memory Organizer | 记忆整理师

A Unity 6 VR narrative experience about deciding how much attention to give different memories. Players sort memory objects into **Focus**, **Context**, or **Background** while moving through an office, a memory room, and a surreal crisis. The final report reflects the player's own arrangement; it does not grade it as right or wrong.

This is a project built with, and extending, **Matt Cabanag's EZPZ Interaction Toolkit**. The toolkit's interaction components and assets remain in this repository; this README describes the Memory Organizer project rather than the toolkit itself. See [Toolkit credit and licenses](#toolkit-credit-and-licenses).

## Experience

1. **Office:** Meet the assistant, explore or learn about the task, and enter the memory space through a crystal ball.
2. **Initial sorting:** Place three surface memories into the attention zones. A missing-memory cue leads into the crisis sequence.
3. **Crisis and mirror chamber:** Encounter the Giant Clown, then work through four branching memory conversations to release the deeper memory objects.
4. **Final sorting:** Return to the memory room and distribute all seven memories among Focus, Context, and Background.
5. **Report:** Return to the office and read a report assembled from each memory's final position before closing the session.

The experience uses authored dialogue and recorded voice clips for its main flow. A separate Convai scene explores live AI conversation; it is an experimental variant, not the default build.

## Open the project

- **Unity Editor:** `6000.4.4f1` (see [`ProjectVersion.txt`](ProjectSettings/ProjectVersion.txt)). Open the repository root as a Unity project and let the Package Manager import the dependencies in [`manifest.json`](Packages/manifest.json).
- **Main VR scene:** [`Assets/__My Project/scene_VR.unity`](Assets/__My%20Project/scene_VR.unity). This is the only enabled scene in the current Build Settings. The project uses XR Interaction Toolkit and OpenXR; VR play requires a compatible headset and the appropriate runtime/device setup. The XR Interaction Simulator can be used for Editor interaction checks.
- **WebGL scene:** [`Assets/__My Project/scene_WebGL.unity`](Assets/__My%20Project/scene_WebGL.unity). Open it directly to inspect or test the desktop/browser adaptation. Select it in Build Settings before making a WebGL build; it is currently disabled there.
- **Convai prototype:** [`Assets/__My Project/scene_VR_ConvaiPrototype.unity`](Assets/__My%20Project/scene_VR_ConvaiPrototype.unity). This scene depends on the Convai Unity SDK (`4.5.0` in the package manifest), a working Convai configuration, and network access. It is also disabled in Build Settings. The main VR and WebGL flows do not use Convai at runtime, although importing the project may require access to the SDK package.

The repository contains Unity source and assets. Open the project in the matching Editor to run or build it.

## Implementation map

| Area | Main code |
| --- | --- |
| Scene and narrative progression, fades, player placement | [`GameStateController.cs`](Assets/__My%20Project/scripts/GameStateController.cs) |
| Office interactions and authored assistant dialogue | [`OfficeDialogueController.cs`](Assets/__My%20Project/scripts/OfficeDialogueController.cs), [`AssistantController.cs`](Assets/__My%20Project/scripts/AssistantController.cs) |
| Memory zones, placement rules, and object state | [`MemoryPlacementController.cs`](Assets/__My%20Project/scripts/MemoryPlacementController.cs), [`MemoryPlacementItem.cs`](Assets/__My%20Project/scripts/MemoryPlacementItem.cs) |
| Branching conversations in the mirror chamber | [`MemoryDialogueController.cs`](Assets/__My%20Project/scripts/MemoryDialogueController.cs) |
| Outcome text based on the final seven placements | [`FinalReportController.cs`](Assets/__My%20Project/scripts/FinalReportController.cs) |
| Experimental Convai-to-Unity narrative integration | [`ConvaiNarrativeBridge.cs`](Assets/__My%20Project/scripts/ConvaiNarrativeBridge.cs) |

The custom project scripts are under `Assets/__My Project/scripts/`. The EZPZ toolkit, XR samples, and other imported asset packs are separate from those custom scripts.

## Toolkit credit and licenses

**EZPZ Interaction Toolkit** was created by [Matt Cabanag](https://www.linkedin.com/in/mattavc/). This project uses its reusable interaction scripts and prefabs as a foundation, alongside Unity XR Interaction Toolkit and project-specific C# systems. The toolkit's original MIT notice and third-party attribution list are retained in [`Assets/README_EZPZ.txt`](Assets/README_EZPZ.txt). Matt's [EZPZ video guides](https://www.youtube.com/playlist?list=PLZP8wzCUfgsKfgJDXuiHHAw-qjcEev1k-) are available for learning the underlying toolkit.

The EZPZ MIT license applies to that toolkit, not automatically to every asset or piece of content in this project. Other imported packages and media may have their own licenses; consult their included notices and source pages before reusing them.
