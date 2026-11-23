# Physical and Connected Product Control

## Purpose

This guide covers accessible control across physical products, assistive control systems, and connected products or environments. It complements media-interface guidance with material on hardware, environmental controls, shared spaces, and system integration.

It is intended for product and interaction designers, engineers, assistive-technology teams, researchers, and AI agents supporting their authorised work. The guidance is product-agnostic; apply it to a specific device only after checking the device, control path, software, and use context.

## 1. Make physical interaction adaptable

People vary in movement, reach, vision, timing, fatigue, communication, and cognitive processing. These needs may change with context and can intersect.

- Design controls for more than one interaction approach where the product allows it: switches, single-switch scanning, user-controlled scanning, multi-switch directed scanning, head control, touch, mouse, joystick scanning, and other assistive inputs.
- Let people adjust scan speed, dwell time, timing, layout, contrast, and text size where those settings are relevant.
- Avoid precision, speed, or a single scanning pattern as the only route to common actions.
- Reduce deep menus and abstract steps; use clear labels, predictable groupings, and recoverable actions.

## 2. Treat hardware as part of the interface

Physical controls are not separate from digital interaction. Consider button layout and grouping, spacing, tactile identification, texture, grip, weight, balance, and physical feedback. Keep related controls easy to distinguish and the result of an action clear.

Make setup, maintenance, and repair manageable for the person and their support network. Minimise unnecessary steps, fragile connections, cables, and repeated technical recalibration. Provide a clear reset and recovery route. Choose wireless or simplified configurations where they improve usability and reliability without creating new access or security barriers.

## 3. Connect controls to system state

A control system should give timely feedback about what changed. Prefer supported, direct, two-way digital interfaces over fragile arrangements that imitate infrared remote signals or chain hardware without a reliable state response.

- Avoid one-way control where the controller cannot learn whether the action succeeded or what state the product is in.
- Return dynamic state to the controller where the system supports it.
- Make status and confirmation perceivable through the person’s available channels.
- Keep control, feedback, and recovery aligned when connectivity is interrupted.

The goal is robust interaction and maintainability, not connectivity for its own sake or over-engineering. Apply security and privacy controls to connected-device pathways.

## 4. Design for shared and private spaces

Shared environments can involve different preferences, privacy needs, and social dynamics. Support individual control without forcing people into a separate or stigmatising experience.

Where appropriate, support profiles and favourites, independent power, channel, browsing, and volume choices, adjustable display intensity, and private use such as a separate room. Make clear which settings affect a person, a device, or everyone using the shared space. Keep the interface consistent with mainstream products where that supports dignity and familiarity.

## 5. Interoperate with the wider assistive ecosystem

Connected control may need to work with communication aids, environmental systems, education tools, entertainment products, and support workflows. Avoid isolating one controller from the wider system a person already uses.

- Prefer extensible, documented control paths where available.
- Preserve meaningful feedback across connected components.
- Avoid duplicating tasks or requiring repeated setup across systems.
- Identify dependencies and who can maintain them before deployment.

## 6. Research and evaluation

Test in realistic environments with the people who will use the product. Evaluate setup, routine control, changing preferences, interruption, connectivity loss, recovery, and maintenance. Treat caregivers as facilitators where appropriate, not substitutes for the user.

Record the product and software versions, control pathway, use context, evidence source, and remaining uncertainty. A simulated user, agent review, or working connection does not establish usability for disabled people.

## Review questions for people and agents

1. Can the person discover and operate the relevant control using a suitable input method?
2. Can they tell what the system did and what state it is in?
3. Can they adjust timing, feedback, or presentation where needed?
4. Does the action remain recoverable after error, interruption, or connectivity loss?
5. Can the person use the product without unnecessary dependence on another person?
6. Can the connected system be maintained without fragile hardware workarounds?
7. Are privacy, security, and shared-space preferences clear?

## Related guidance

- [Connected TV](Connected_TV.md) covers television and connected-TV journeys and remote-specific use.
- [Accessible Interactive Media Control](Accessible_Interactive_Media_Control.md) covers media-specific interaction requirements.
- [Inclusive Multimodal UX](https://github.com/Double-FW/Inclusive-Multimodal-UX) covers general modality choice and continuity.
