# Accessible Interactive Media Control

## Purpose

This guide covers user control of television, streaming, and other interactive media experiences. It focuses on media-specific interaction requirements and routes broader physical-device, environmental-control, and system-integration guidance to [Physical and Connected Product Control](Physical_and_Connected_Product_Control.md).

**Provenance:** The available source material refers to user-centred development work but does not identify its organisation, research body, participants, methods, or publications. Treat this guide as transferable design themes, not evidence from a named study. Do not reconstruct missing citations or participant details. Add references only if the underlying sources are recovered and verified.

## Design requirements

### Start with lived experience and the full context

Do not assume what people with complex motor, cognitive, sensory, or communication needs require. Involve disabled people in requirements, interaction design, and evaluation. Adapt research and communication to participants. Caregivers and support networks may facilitate participation but should not replace the person’s views.

Consider interacting needs together. Motor control can intersect with cognition, vision, fatigue, medication effects, communication, and whether media is used in a shared or private space. Avoid designing for a single impairment category or an ideal environment.

### Make cause and effect clear

Latency can break trust, particularly for people using scanning, dwell selection, head-controlled input, switches, or other assistive methods.

- Minimise avoidable response delay.
- Show or speak a clear confirmation when an action is accepted.
- Make state changes visible or otherwise perceivable and consistent.
- Avoid silent failures and unnecessary sequential steps for common actions.

### Support adjustable and flexible interaction

Fixed interfaces can exclude people with different movement, vision, timing, and cognitive needs. Where appropriate, let people adjust scanning speed, dwell time, layout, contrast, text size, and volume step size. Support user profiles when media is shared, and preserve choice about whether preferences persist.

Support interaction patterns suited to the person and task, including single-switch auto-scanning, user-controlled scanning, multi-switch directed scanning, touch, mouse, joystick scanning, and head control where the product supports them. Do not assume that one scan pattern, gesture, or input method suits everyone. Reduce deep menus and abstraction; allow people to correct or interrupt an action.

### Manage cognitive load

- Limit the number of choices presented at once where this helps the task.
- Use familiar, recognisable symbols, with clear labels or other ways to understand their meaning.
- Prefer predictable layouts and shallow navigation for common media tasks.
- Use overlays or focused transitions where they preserve context better than replacing the whole view.
- Keep the current location, selection, and playback state clear.

### Make feedback fit the viewing context

Programme audio can mask sound cues, while small or subtle visual changes can be hard to perceive at a distance. Do not rely on audio alone, colour alone, or micro-changes in the interface.

Make navigation, selection, playback, and scan-group state perceivable in the viewing context. Ensure that feedback is timely and that people using assistive input can tell when an action has succeeded, failed, or needs another step.

### Preserve agency and dignity

People should be able to explore and control media without routine dependence on another person. Support independent access to power, channel or content selection, volume, browsing, and playback when those functions are available. Avoid designs that make accessible interaction look or feel stigmatising.

## Cross-cutting review questions

- Where does latency weaken the link between an action and its result?
- Which routine media tasks require another person’s intervention, and why?
- Can scanning, timing, or other relevant interaction demands be adjusted?
- Does the interface recover gracefully when ability, context, or connectivity changes?
- Can people use the system without specialist maintenance for ordinary tasks?
- Is feedback immediate and perceivable in the real viewing environment?
- Are personal choices supported in shared and private use?

## Expected outcomes

A well-designed interactive media experience aims to support adoption, sustained use, satisfaction, clear cause and effect, adjustable interaction, manageable cognitive demand, context-aware feedback, dignity, agency, and sustainable everyday use. These are design aims, not evidence that a particular product has achieved them.

## Terminology and evidence

Use [Terminology and Principles](https://github.com/Double-FW/Terminology-and-Principles), checking the relevant entry’s status and scope. Keep participant report, observed behaviour, interpretation, hypothesis, and synthetic material distinct. Do not treat design aims or agent review as user evidence or conformance.

## Related guidance

- [Connected TV](Connected_TV.md) covers TV setup, navigation, remote interaction, access-service discovery, spoken output, documentation, and evaluation.
- [Physical and Connected Product Control](Physical_and_Connected_Product_Control.md) covers physical controls, environmental systems, hardware integration, and control ecosystems.
- [Inclusive Multimodal UX](https://github.com/Double-FW/Inclusive-Multimodal-UX) covers general cross-modal principles.
