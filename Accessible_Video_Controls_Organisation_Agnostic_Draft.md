# Accessible Video Controls — Organisation-Agnostic

**Status:** Review draft  
**Purpose:** Organisation-agnostic adaptation of guidance about custom HTML5 video controls. This is a draft for review, not an approved standard or a conformance assessment.

## Purpose

Custom video controls should make playback accessible and straightforward to operate. This guide describes a baseline for web video, the requirements to consider when replacing native browser controls, and the behaviours users need from a player.

The examples use generic HTML and CSS. They are illustrative starting points: test the implementation with the browsers, devices, and assistive technologies in scope.

## 1. Start with usable video and native controls

Use the standard HTML `<video>` element. Before adding custom controls, provide native browser controls so the video remains usable if customisation has not loaded or fails.

Provide a suitable source format and, where it is useful, a direct way to download or otherwise access the media if the browser cannot play it. Provide captions or subtitles for video with dialogue and relevant audio information. Make captions available through the player or leave native controls available so users can reach the browser’s caption controls.

Example baseline:

```html
<video controls preload="metadata">
  <source src="media/video.webm" type="video/webm">
  <source src="media/video.mp4" type="video/mp4">
  <track
    kind="captions"
    src="media/captions-en.vtt"
    srclang="en"
    label="English">
  <p>
    Your browser cannot play this video.
    <a href="media/video.mp4" download>Download the video</a>.
  </p>
</video>
```

Confirm that the caption track is accurate, synchronised, correctly labelled, and available in the languages the service intends to support. A player control cannot compensate for a missing or poor-quality access service.

## 2. Add custom controls progressively

Do not remove the native controls until the custom controls are ready and working. Keep the custom controls hidden before JavaScript has successfully enhanced the player. If enhancement fails, the native player must remain usable.

A custom player can group the video and its controls so assistive technologies can identify them as related:

```html
<div role="group" aria-labelledby="player-title">
  <h2 id="player-title">Video title</h2>
  <video controls>
    <source src="media/video.mp4" type="video/mp4">
    <track
      kind="captions"
      src="media/captions-en.vtt"
      srclang="en"
      label="English">
  </video>

  <div hidden>
    <!-- Custom controls are shown only after they are ready. -->
  </div>
</div>
```

Once the custom controls are fully initialised, they can be shown and native controls can be disabled. Test this transition, media-loading errors, and script failures. Avoid exposing duplicate native and custom controls at the same time.

## 3. Use clear, operable controls

Use native `<button type="button">` elements for button actions. Give each control a clear accessible name that matches its purpose and icon. For a play/pause toggle, the accessible name may change between “Play” and “Pause” as the state changes. Apply the same approach consistently to mute/unmute and other toggles. Make sure the name and visual state stay in sync with playback.

Some toggle patterns keep a stable label and expose a pressed state instead. If that approach is used, make sure the name and state together are clear and do not announce contradictory information. Test the chosen pattern with screen readers and speech input.

Hide decorative icons from assistive technologies and keep them out of keyboard focus. The text label, including a visually hidden label when needed, must provide the control’s name.

Example pattern:

```html
<button type="button" aria-label="Play">
  <svg aria-hidden="true" focusable="false" viewBox="0 0 24 24">
    <!-- Decorative play icon -->
  </svg>
</button>
```

Do not rely on an icon, colour, position, or sound alone to explain what a control does or whether it is active.

## 4. Make the timeline accessible

The timeline has two jobs: communicate current progress and let the user seek to a different point. A labelled native range input is a robust starting point:

```html
<label for="video-timeline">Video timeline</label>
<input
  id="video-timeline"
  type="range"
  min="0"
  max="95.2"
  value="14.7">
```

Keep the range’s minimum, maximum, and current value synchronised with the media duration and playback position. Values may be represented in seconds internally. Where a formatted time is useful to assistive technology, provide a human-readable value text such as “14 seconds” or “1 minute, 35 seconds”, while keeping the actual range value numeric. Do not put text into a numeric value field.

The timeline must be keyboard operable. People should be able to focus it and use the keyboard to move through the media. Make the current position and the result of seeking perceivable. Do not announce every second of playback through a live region; frequent updates can overwhelm screen-reader users.

## 5. Design visible, adaptable controls

Controls should be large enough to target by mouse and touch, with clear focus styles. Keep the layout usable as the number of controls changes and at narrow viewports or enlarged zoom.

The timeline may take the remaining available space between buttons, but it must remain operable at different sizes. Custom styling should not make controls disappear in high-contrast or forced-colours settings. Check focus visibility, contrast, and distinct states such as selected, muted, unavailable, and active.

Example focus style:

```css
.video-player button:focus-visible,
.video-player input:focus-visible {
  outline: 3px solid currentColor;
  outline-offset: 2px;
}
```

Use colours that meet the applicable contrast requirements in the actual player context. Do not rely on colour alone to show focus, selection, playback, or mute state.

## 6. Avoid disruptive autoplay

Do not start video or audio automatically by default. Unexpected sound can interfere with assistive technology and disturb people using the page in shared or quiet settings.

If a user has explicitly opted in to autoplay, start muted. Make pause, stop, and mute controls obvious and immediately available. Make it easy to turn autoplay off, including when it has been enabled unintentionally. Test that playback cannot obscure screen-reader speech or prevent users from finding the control that stops it.

## 7. Keep playback state accurate

The interface must reflect the actual media state. Update the play/pause name and icon when playback starts, pauses, or ends. When playback ends, return the play control to its inactive/play state so it is ready for another play.

The timeline should reflect the current playback position and should update the media position when the user moves it. Provide feedback when an action is accepted where needed. Handle buffering, unavailable media, and playback errors without leaving controls in a misleading state.

Do not make controls accessible only on hover. If controls fade or hide during playback, keep them visible while keyboard focus is within the player, and provide a predictable way to reveal them again.

## Review checklist

- Native controls work before custom controls are ready and if enhancement fails.
- Every custom control has an understandable name, role, and current state.
- Keyboard users can reach and operate every function without becoming trapped.
- The tabbing order starts with play/pause then mute/unmute then the rest of the controls using a visual tabbing order.
- Focus is visible and is not obscured by overlays or fading controls.
- Play/pause and mute/unmute states remain accurate throughout playback.
- The timeline is labelled, keyboard operable, and exposes understandable position information.
- Target sizes, layout, and focus styling work at relevant viewport sizes and zoom levels.
- Controls remain perceivable in high-contrast or forced-colours modes.
- On/Off controls for Captions and Audio Description must be persistently in the main interface and not in a dropdown or menu.
- Captions and other supplied access services are discoverable and selectable.
- Caption display must support all aspects of best practice (https://github.com/Double-FW/Closed-Caption-Subtitles/blob/main/Closed_Caption_Subtitle_Guidelines.md).
- Autoplay does not start unexpectedly; when explicitly enabled, playback begins muted and can be stopped or muted immediately.
- The player is manually checked with relevant browsers, devices, assistive technologies, and alternative input methods.

## Source and adaptation note

This draft adapts interaction and implementation guidance from the [Video controls page in the BBC GEL design system](https://bbc.github.io/gel/components/video-controls/). The source page identifies itself as published version 0.1.0. Organisation-specific names, classes, and branding have been removed or generalised. Example markup and styling have been rewritten as generic illustrations; they are not copied production code.

Before adopting this guidance, review the examples against current HTML, ARIA, WCAG, browser, and assistive-technology behaviour. In particular, validate the player’s accessible range values and high-contrast styling in the target environments. This document is not an endorsement by the source organisation and does not establish accessibility or conformance.
