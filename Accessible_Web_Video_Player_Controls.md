# Accessible Web Video Player Controls

## Purpose

This guide helps teams design and review controls for HTML video players on websites and in web applications. It focuses on the player interface and its operation. It complements, rather than replaces, the broader interaction principles in [Accessible Interactive Media Control](Accessible_Interactive_Media_Control.md).

This is practitioner guidance. It is not a complete WCAG audit, a legal assessment, or evidence that a particular player is accessible. The right controls and behaviour depend on the player, browser, device, assistive technology, media, and user task.

## Scope boundaries

This guide covers:

- selecting native or custom web player controls;
- semantics, accessible names, states, focus, input, and feedback;
- playback, seeking, volume, display, captions, and other available access services;
- progressive enhancement and fallback;
- practical review and testing.

It does not specify how to create accurate captions, subtitles, audio description, sign-language content, or transcripts. Use the relevant specialist guidance for media production and access-service authoring. A player can expose an access service correctly while the service itself remains incomplete or inaccurate.

## Start with a suitable player

Prefer a well-maintained player with documented accessibility support over building a custom player from scratch. Review the actual player version and configuration: accessibility can vary between releases, themes, plugins, embeds, and browser/device combinations.

Native browser controls provide a useful baseline and may expose platform-specific capabilities. Their appearance and available features differ across browsers and operating systems, so assess whether they meet the service's needs. If custom controls are necessary, retain a working native-controls fallback until the custom interface is ready. A script failure must not leave users with an unplayable video or no usable controls.

Do not hide native controls before the replacement controls work. Test failure and loading states as well as the fully enhanced player.

## Controls and accessible names

Provide controls for the actions the service supports and people need. Depending on the use case, these may include:

- play or pause;
- seeking and current position;
- volume and mute;
- captions or subtitles, including language selection where available;
- audio description or alternative audio tracks where available;
- playback speed;
- full-screen or expanded display;
- transcript access or chapter navigation where provided.

Do not show a control that appears available but cannot be used for the current media. Explain unavailable tracks or features in a way that users can perceive.

Use native HTML buttons and inputs where they fit the interaction. Give every control a clear accessible name that describes its action. An icon by itself is not a reliable name. Hide decorative icons from assistive technology and keep them out of the keyboard focus order.

For toggle actions, use one clear state pattern. For example, a button can expose the next action in its name (such as “Play” or “Pause”), or keep a stable name and expose its pressed state. Avoid contradictory names and state announcements. Confirm that names and state remain synchronised with playback, including after media ends, errors, or external playback changes. Use `type="button"` for buttons that are not intended to submit a form.

Group related controls so their relationship is understandable, without adding redundant announcements. If the player has a visible title, make the player region identifiable by that title where the implementation allows it.

## Keyboard and other input

Make every operation available without a pointer. At minimum, check that people can:

- move to and from each control using the expected keyboard navigation;
- operate buttons, menus, toggles, and sliders using their native keyboard behaviour;
- seek accurately enough for the task;
- close menus and overlays and return to the point they left;
- use the player without becoming trapped in it.

Do not intercept common keys in a way that prevents browser, assistive technology, or operating-system commands from working. If the player provides shortcut keys, make them discoverable, avoid conflicts, and provide a way to disable or change them where practical.

Test with speech input, switch or scanning input, and other relevant assistive methods. A pointer-only scrubber, tiny target, or rapidly moving focus target can make a technically keyboard-operable control difficult to use in practice.

## Seek timeline and playback position

The timeline must communicate both current position and the means to seek. Prefer a native range input with a programmatic label when it meets the design needs. If a custom slider is used, implement and test its complete keyboard interaction, role, name, minimum, maximum, current value, and value changes according to current WAI-ARIA guidance.

Represent the range values programmatically as values of the correct type. If a formatted time such as “1 minute 24 seconds” is useful to screen reader users, expose it as a human-readable value text where supported; do not replace a numeric range value with arbitrary text. Update the value when playback or seeking changes it.

Avoid announcing every playback time update through a live region. Repeated announcements can make the rest of the page difficult to use. Make the current position available when a person focuses or operates the timeline, and provide concise feedback after a seek when useful. Ensure buffered, loaded, and played portions are distinguishable without relying on colour alone.

Check whether the seek step and control size work for the media length, target devices, and available input methods. Support coarse and precise seeking where the task calls for both.

## Focus, visibility, and layout

Every focused control needs a visible focus indicator that remains distinguishable against the player and nearby content. Do not remove browser focus outlines without providing an equally clear replacement.

Keep controls large enough to operate with the available input methods and avoid placing adjacent targets so close that accidental activation is likely. Preserve control visibility at different zoom levels and viewport sizes. Check that controls do not cover important video content or captions, and that captions remain readable when controls appear.

Custom styling must preserve contrast and visibility in forced-colours or other high-contrast settings. Include non-colour cues for selected, enabled, muted, focused, and unavailable states. Test the player at the text and page zoom levels relevant to its layout.

## Playback, feedback, and interruption

Keep the interface state in sync with the actual media state. A control should not say “Pause” while the video is stopped, or show an active state after playback has ended. Make buffering, playback errors, and unavailable media understandable and provide a practical next step where possible.

Avoid starting sound or motion unexpectedly. Do not start playback automatically by default. If a user has explicitly enabled autoplay, prevent unexpected audio from masking assistive technology or disrupting the surrounding task, and make pause, stop, mute, and autoplay controls easy to find. Respect browser and operating-system preferences and policies.

Do not make controls appear only on hover. If controls auto-hide during playback, make the behaviour predictable, ensure keyboard focus keeps the controls available, and provide a reliable way to reveal them again. Do not allow transient feedback to disappear before it can reasonably be perceived.

## Captions, subtitles, and other access services

When the media provides captions or subtitles, make their availability and selection discoverable and operable. Identify languages clearly. Keep captions legible against the video and allow useful presentation adjustments when supported by the player. Do not imply that captions are available when no usable track exists.

Where audio description, sign-language video, or alternative audio tracks are provided, expose them in a clear and consistent way. Preserve the selected option as appropriate, while allowing the person to change it. Do not assume a person wants a particular access service based on a disability label.

Offer transcripts or chapters where they support the service and content. Make any link or transcript interaction understandable without relying on visual position alone. The quality and completeness of captions, description, sign language, and transcripts must be assessed separately from the player controls.

## Review checklist

For the player version and configuration being released, confirm:

- A usable control set is available before and after enhancement, including when scripts fail.
- All controls have clear names, correct semantics, and accurate states.
- Every function works with keyboard alone and there is no keyboard trap.
- Focus is visible and remains visible when controls are shown or hidden.
- Timeline values and seeking work with keyboard, screen reader, and relevant alternative input.
- Playback updates do not create a stream of disruptive announcements.
- Control targets and layout work at expected viewport sizes and zoom levels.
- Controls remain visible in high-contrast or forced-colours settings.
- Captions and other available access services can be found, selected, and used.
- Autoplay, buffering, errors, ended playback, and auto-hiding controls are handled clearly.
- Checks include the actual browsers, devices, assistive technologies, and media configurations in scope.

Automated checks can identify some markup problems, but they cannot establish that player controls work well for people. Include manual interaction checks and, where feasible, evaluation with disabled people who use the relevant technologies.

## Standards and evidence

Map the implementation to the applicable WCAG 2.2 success criteria for the service and content. Relevant areas may include keyboard access, focus, names and states, contrast, target size, captions, and audio description. This list is not exhaustive and does not determine conformance. Record the tested player version, browser/device combinations, access services, methods, findings, and unresolved limitations.

The BBC GEL video-controls page is a useful source for custom-control examples and interaction considerations. It is marked version 0.1.0; treat its code as an example to review, not as current normative implementation guidance. In particular, verify ARIA value handling, browser support, and high-contrast techniques against current standards and target environments before adopting snippets.

## Sources

- BBC GEL, [Video controls](https://bbc.github.io/gel/components/video-controls/) (published, version 0.1.0; accessed 24 November 2026).
- W3C WAI, [Media Players](https://www.w3.org/WAI/media/av/player/).
- W3C WAI, [Making Audio and Video Media Accessible](https://www.w3.org/WAI/media/av/).
- WHATWG, [HTML Standard: Media elements](https://html.spec.whatwg.org/multipage/media.html).
- W3C, [Web Content Accessibility Guidelines (WCAG) 2.2](https://www.w3.org/TR/WCAG22/).
- W3C WAI, [ARIA Authoring Practices Guide: Slider Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/slider/).

These sources inform this guide; they do not constitute research with users of this repository's guidance or evidence that any particular implementation is accessible.
