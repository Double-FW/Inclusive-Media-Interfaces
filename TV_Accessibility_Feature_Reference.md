---
title: "TV Accessibility Feature Reference"
version: "1.0.0"
date: "2026-11-23"
author: "Double FW"
language: "en-GB"
status: "cross-platform practitioner reference"
artifact_type: "feature-reference"
scope: "Television, connected-TV, streaming interfaces, physical controls, and synchronized second-screen control"
license: "MIT"
license_source: "Inclusive-Media-Interfaces/LICENSE"
review_status: "owner review required"
---

# TV Accessibility Feature Reference

## Purpose

This reference groups digital and physical accessibility features documented across television, connected-TV, streaming, remote-control, and second-screen examples. For each feature it records where an example is documented, the design approach, a practical method, techniques, and the intended outcome for an individual.

Platform names identify examples, not endorsements. Product, model, operating-system, region, service, content, and software-version differences matter. A feature listed in a platform’s support material is not evidence that it is available on every device, is usable in every context, or has been evaluated with disabled people.

The feature recommendations below are anonymised: feature names and explanations use generic descriptions rather than vendor terminology. Platform names remain in the coverage field so readers can trace where a documented example appears. Source URLs are collected only in the source register at the end; feature entries refer to source IDs, not to source links.

## Scope and boundaries

This file covers interface and control design: setup, navigation, visual and spoken presentation, programme-guide access, access-service discovery and control, physical remotes, alternative control clients, state feedback, preferences, and synchronization between a television and a personal device.

It does not specify how captions, subtitles, audio description, signing, or other programme access services are authored, produced, transmitted, or quality controlled. Use the specialist Double-FW repositories for those subjects:

- [Closed Caption Subtitles](https://github.com/Double-FW/Closed-Caption-Subtitles) for caption and subtitle terminology, authoring, and delivery.
- [Audio Descriptions](https://github.com/Double-FW/Audio-Descriptions) for audio-description planning and production.
- [Accessible Film, TV and Video Content Production Management](https://github.com/Double-FW/Accessible-Film-TV-and-Video-Content-Production-Management) for accessible media production workflows.

This reference applies those services only as interface options to discover, select, control, and verify. Do not infer availability from an icon or setting alone: distinguish whether a service exists for the content, is findable, can be selected, activates, and works during playback.

## How to use this reference

Each feature has a status:

- **Documented example** — a platform or project source describes the feature. This does not prove universal availability or usability.
- **Historical prototype or project reference** — a research or demonstration source illustrates an architecture or interaction. It is not a current product standard or proof of deployment.
- **Design recommendation** — a cross-platform recommendation for teams to evaluate and implement where appropriate. It may go beyond what the cited platforms currently document.

For a product decision, identify the exact device, software, region, service, content, task, control method, and environment. Check the current implementation, then evaluate it with people who use the relevant access methods. Treat expected individual outcomes as hypotheses until evaluated.

## Terminology and alignment

Use the current entry status and scope in [Double-FW Terminology and Principles](https://github.com/Double-FW/Terminology-and-Principles/blob/main/START_HERE.md). A glossary entry marked proposed is not an adopted definition. Retain the source or sector meaning where it is more specific, and record ambiguity rather than silently resolving it.

In this reference:

- **Captions** and **subtitles** are not assumed to be interchangeable. Their meaning and coverage depend on the source, language, and service specification. Route content detail to the specialist repositories above.
- **Programme audio description** means the access service for relevant visual information in a programme. **Spoken interface guidance** means speech that explains device or application controls, focus, status, or setup. Do not conflate the two.
- **Access-service availability**, **discovery**, **selection**, **activation**, and **successful playback** are separate states.
- **Default on** means a service is enabled when first setting up or creating a new profile, with a clear and simple way to switch it off. Once a person makes an explicit choice, respect it within the stated preference scope.
- A modality is an available way to perceive or operate an interface. Do not assign one modality or preference to a whole disability group.

## Feature index

| ID | Group | Feature |
|---|---|---|
| F01 | Setup and spoken interface | Spoken guidance during first-run setup |
| F02 | Setup and spoken interface | Semantic screen-reader access and consistent focus |
| F03 | Visual presentation and motion | Adjustable visual presentation |
| F04 | Visual presentation and motion | Reduced motion and preview control |
| F05 | Discovery and programme guides | List and grid programme-guide views |
| F06 | Discovery and programme guides | Find and filter content by access-service availability |
| F07 | Discovery and programme guides | Captions/subtitles enabled by default, with direct opt-out |
| F08 | Physical controls | Dedicated physical controls for captions/subtitles and audio description |
| F09 | Alternative control | Accessible second-device and alternative input control |
| F10 | Feedback and continuity | Clear action feedback, state, and recovery |
| F11 | Profiles and preferences | User-controlled preference persistence and scope |
| F12 | Synchronized experiences | Synchronized second-screen access and control |
| F13 | Connected control architecture | Semantic control interface with state and secure pairing |

## Feature guidance

### F01. Spoken guidance during first-run setup

**Status:** Documented examples; design recommendation.

**Documented coverage:** Apple TV; Android TV/TalkBack-capable devices; Panasonic television models; Sony BRAVIA models; Samsung television models; Sky Q, Sky Glass and Sky Stream; BT TV/YouView. Exact setup behaviour and availability vary by product and software. (S01–S08, S11–S15)

**Design approach:** Make setup usable without requiring a person to see every screen or already know the sequence. Spoken guidance is an interface access mode, not programme audio description.

**Method:** At the start of first-run setup, announce that spoken guidance is active and explain how to pause, repeat, adjust, or turn it off. Keep the choice immediately available throughout setup. Do not require a sighted helper or a prior trip through inaccessible settings to find it.

**Techniques:** Enable spoken interface guidance by default during setup; provide a clear, low-effort opt-out; give concise speech for focus, labels, instructions, errors, and progress; allow adjustment of speech rate, volume, and language where supported; avoid speaking irrelevant visual detail; retain an accessible route to re-enable guidance after setup.

**Intended individual outcome:** A person who benefits from speech can understand and complete initial setup independently, while a person who does not want speech can stop it promptly without losing setup context.

**Evidence limits:** Vendor documentation describes varying voice-guidance or screen-reader features; it does not establish that all setup flows start with speech enabled. Default-on setup guidance is a recommendation, not a claim about current platform defaults.

**Sources:** S01–S08, S11–S15.

### F02. Semantic screen-reader access and consistent focus

**Status:** Documented examples; design recommendation.

**Documented coverage:** Apple TV; Android TV; Sony BRAVIA; Samsung TV; Sky Q, Sky Glass and Sky Stream; Freeview Accessible TV Guide; BT TV/YouView. (S01–S08, S10–S14)

**Design approach:** Expose the structure and state of the interface so that spoken and other assistive-technology output supports the same meaningful tasks as the visual interface.

**Method:** Inspect the interface’s accessible names, roles, order, focus movement, current selection, status, and action results across setup, menus, guide, search, playback, and settings. Verify consistency when moving between a platform shell and third-party applications.

**Techniques:** Give controls meaningful names and roles; announce current focus and changed state; maintain predictable focus order and return focus after closing a view; expose headings, groups, selected states, and actionable results; avoid inaccessible custom controls; announce errors and recovery choices. Where a remote app is offered, make its controls compatible with the phone’s screen reader and accessibility settings.

**Intended individual outcome:** A person using a screen reader can locate, understand, and operate controls without losing orientation or relying on sighted assistance.

**Evidence limits:** Feature availability and implementation differ across models, operating systems, and apps. A platform screen reader does not guarantee that every third-party app is compatible.

**Sources:** S01–S08, S10–S14.

### F03. Adjustable visual presentation

**Status:** Documented examples; design recommendation.

**Documented coverage:** Apple TV and its TV app; Android TV caption settings; Sony BRAVIA; Samsung TV; Freeview Accessible TV Guide; Sky Q, Sky Glass and Sky Stream. (S01–S04, S07–S10, S12–S14)

**Design approach:** Let people change the visual presentation to suit viewing distance, contrast needs, lighting, and visual preferences without hiding information or breaking the interface.

**Method:** Check settings and real content at typical viewing distances and across menus, guides, overlays, and playback. Test enlarged text, magnification, contrast, focus visibility, colour differentiation, transparency, and display adaptation together.

**Techniques:** Support scalable text and magnification; provide high-contrast presentation and a clearly visible focus indicator; do not use colour alone to convey meaning; preserve legibility and layout at larger text sizes; allow caption/subtitle appearance controls where the platform provides them, while routing the content presentation specification to the specialist repository; expose colour or display adaptations without assuming one setting fits everyone.

**Intended individual outcome:** A person can perceive and distinguish interface information at their preferred size and contrast, including from a typical sofa-to-screen distance.

**Evidence limits:** Specific options and supported applications vary. A setting in the operating system may not affect every application or video overlay.

**Sources:** S01–S04, S07–S10, S12–S14.

### F04. Reduced motion and preview control

**Status:** Documented examples; design recommendation.

**Documented coverage:** Apple TV app includes reduced-motion and autoplay-preview controls on supported devices. (S02)

**Design approach:** Avoid making animated transitions or unsolicited video previews the only way to understand or explore content.

**Method:** Review home screens, guide transitions, search results, focus changes, and promotional content. Check whether motion is necessary, can be paused, and respects available operating-system or application preferences.

**Techniques:** Provide reduced-motion settings; allow autoplay previews to be disabled; avoid flashing or strobing content in interface chrome; keep essential information available in a stable text or still-image form; preserve clear focus movement when transitions are reduced.

**Intended individual outcome:** A person can explore and navigate with less unwanted motion, distraction, or visual discomfort while retaining access to the same information.

**Evidence limits:** The cited documentation does not imply that these controls are available in all TV apps or all products.

**Sources:** S02.

### F05. List and grid programme-guide views

**Status:** Design recommendation; cited platform documentation does not establish universal support for both views.

**Documented coverage:** Freeview and Ofcom sources describe electronic programme guide access and accessibility, but the reviewed sources do not verify that every named platform offers both list and grid modes. (S09–S10)

**Design approach:** Offer more than one way to scan schedule information because a time-by-channel grid and a linear list impose different visual, spatial, and navigation demands.

**Method:** Provide both list and grid views, let each person choose or switch between them, and evaluate common tasks such as finding a programme by title, time, channel, or access-service availability.

**Techniques:** Keep content, filters, and selected programme when switching views; give clear labels for view choice; preserve meaningful focus location; make list and grid operable with remote, keyboard, screen reader, and other supported inputs; provide a non-spatial alternative to dense time-by-channel scanning; announce programme title, channel, time, and available service information as a coherent unit.

**Intended individual outcome:** A person can choose the guide structure that best supports their way of scanning and comparing programmes, without losing their search or selection.

**Evidence limits:** This is a cross-platform recommendation. Do not state that a particular platform supports both views unless verified on the target device and software version.

**Sources:** S09–S10; design synthesis.

### F06. Find and filter content by access-service availability

**Status:** Documented examples; design recommendation.

**Documented coverage:** Freeview Accessible TV Guide; Sky Q, Sky Glass, Sky Stream and Sky+; BT TV/YouView. (S09, S12–S15)

**Design approach:** Make service availability visible during content discovery so a person can choose what to watch before starting playback.

**Method:** Check programme listings, search results, content details, recording options, and playback controls. Trace whether displayed availability corresponds to the exact programme version and whether a selection can actually be activated.

**Techniques:** Show clear, text-supported indicators for the access services that are available; offer filters where listings support them; retain the information through recording and playback where technically supported; expose the same status to spoken interfaces; explain when availability is unknown or differs by episode, version, or service. Keep availability, discovery, selection, activation, and successful use as distinct states.

**Intended individual outcome:** A person can identify and select content likely to meet their access needs before investing time in playback, and can tell if the expected service is not present.

**Evidence limits:** This concerns interface discovery and control only. It does not set requirements for captions, subtitles, audio-description, or signing production, editorial quality, or delivery. See specialist repositories in Scope and boundaries.

**Sources:** S09, S12–S15.

### F07. Captions/subtitles enabled by default, with direct opt-out

**Status:** Design recommendation.

**Documented coverage:** Platforms in scope document caption/subtitle settings and controls, including Apple TV, Android TV, Sony BRAVIA, Samsung TV, Freeview, BT TV/YouView, and Sky products. The reviewed documentation does not establish a universal default-on behaviour. (S02–S04, S07–S09, S11–S14)

**Design approach:** Reduce the effort required to obtain text access while preserving personal choice and a direct way to switch it off.

**Method:** Enable captions/subtitles by default during first-run setup and for a new profile, and clearly tell the person this is active. If the person switches them off, respect that explicit choice for the relevant profile or device scope. Make it easy to switch them back on.

**Techniques:** Provide a one-action remote or on-screen route to switch captions/subtitles on or off; state whether the setting applies to the current programme, profile, app, or device; do not silently reset a saved preference each time playback starts; provide clear feedback about the selected language/service and whether it is available for the current content. Maintain a usable interface if the service is unavailable.

**Intended individual outcome:** A person who benefits from text access receives it without having to find a buried setting, while a person who does not want it can turn it off and have that choice respected.

**Evidence limits:** This is an explicit design recommendation, not a description of current platform defaults or a guarantee that a programme offers captions/subtitles. Do not infer content quality or coverage from the setting. Route content and delivery detail to [Closed Caption Subtitles](https://github.com/Double-FW/Closed-Caption-Subtitles).

**Sources:** S02–S04, S07–S09, S11–S14; design synthesis.

### F08. Dedicated physical controls for captions/subtitles and audio description

**Status:** Documented examples of access shortcuts; design recommendation for dedicated controls.

**Documented coverage:** Sky remote controls provide accessibility-oriented remote options and shortcuts; BT TV/YouView documents an AD button on a compatible remote. Other sources document access-service settings or model-specific shortcuts rather than a universal pair of dedicated keys. (S07, S15–S17)

**Design approach:** Put high-value access controls within direct physical reach, reducing dependence on visual menu search, memory, or precise navigation.

**Method:** Include distinct, dedicated physical buttons for captions/subtitles and programme audio description on standard remotes where product design permits. Test their location, tactile identification, accidental activation risk, and operation from common viewing positions.

**Techniques:** Use distinct labels and tactile differentiation; place the buttons consistently and explain them accessibly; make each action direct and reversible; announce or display current state; clarify when a service is unavailable for the selected content; avoid assigning the same ambiguous key to different actions across related products. Retain accessible menu and alternative-control routes for people who cannot use the physical buttons.

**Intended individual outcome:** A person can directly enable or disable a preferred access service without navigating a deep menu and can tell whether the action worked.

**Evidence limits:** Dedicated buttons are a recommendation. Source documentation confirms some shortcuts and models, not that every remote has separate dedicated subtitle/caption and AD buttons. A shortcut does not guarantee that the service is available or activated. Route service production/delivery to the specialist repositories.

**Sources:** S07, S15–S17; design synthesis.

### F09. Accessible second-device and alternative input control

**Status:** Documented examples; design recommendation.

**Documented coverage:** Sony describes a screen-reader-compatible smartphone app; Sky describes an accessible remote app; BT TV/YouView documents USB keyboard support for some tasks. The Universal Control API slide deck is a historical prototype. (S05, S15, S22, S30–S31)

**Design approach:** Provide more than one way to operate a television interface and allow a person to use an input method that suits them, including a personal device they already know.

**Method:** Support compatible input routes such as accessible mobile apps, keyboards, switch or other assistive control, and voice where implemented. Ensure essential tasks do not depend on a single input mode or a proprietary phone platform.

**Techniques:** Make remote apps work with the mobile operating system’s screen reader and accessibility settings; expose meaningful control names and state; support predictable focus and adequate target size; include key alternatives for common tasks; make pairing discoverable and reversible; communicate network, battery, or connection loss; apply least-privilege access and protect viewing or profile data.

**Intended individual outcome:** A person can choose an available input route that matches their movement, vision, communication, or cognitive needs, and can recover when a device disconnects.

**Evidence limits:** App compatibility and control coverage vary by model, platform, and region. A phone app is not a substitute for accessible controls on the television itself. Historical prototypes are not current deployment evidence.

**Sources:** S05, S15, S22, S30–S31.

### F10. Clear action feedback, state, and recovery

**Status:** Documented examples; design recommendation.

**Documented coverage:** Panasonic describes adjustable voice guidance; Samsung and Sky describe spoken menu guidance; Sony documents screen-reader and magnification features. The BBC Universal Control API materials discuss control feedback and state as a research architecture. (S05–S06, S08–S11, S18–S20, S30–S31)

**Design approach:** Make the result of an action perceivable and recoverable through the person’s available output methods, especially when remote interaction is delayed or the TV is used at a distance.

**Method:** For common actions, test whether the system confirms acceptance, reports the resulting state, identifies failure, and offers a next step. Evaluate with speech, visual output, and other supported feedback together.

**Techniques:** Provide timely confirmation for play/pause, volume, selected settings, guide view, and access-service controls; make error feedback specific and actionable; avoid relying on a brief colour-only flash or sound alone; prevent repeated remote presses from causing hidden queued actions; provide a clear cancel, undo, retry, or return route; announce changes in spoken interface guidance without narrating irrelevant events.

**Intended individual outcome:** A person can understand what the system did, detect when it did not work, and recover without guessing or restarting the task.

**Evidence limits:** Feedback described in a support page or prototype does not show that every interaction is covered or that feedback timing works in practice. The Universal Control API is historical research, not a current standard.

**Sources:** S05–S06, S08–S11, S18–S20, S30–S31.

### F11. User-controlled preference persistence and scope

**Status:** Documented examples; design recommendation.

**Documented coverage:** Sky documentation describes settings that persist in supported products; Freeview describes returning to the accessible guide with preferences retained; Apple documents accessibility options. Behaviour varies by setting and platform. (S02, S12, S18–S21)

**Design approach:** Retain an explicit preference where it helps, while making clear what it affects and giving people control over its scope.

**Method:** For each preference, state whether it applies to a person/profile, device, application, content session, or connected second screen. Test profile switching, guest use, sign-out, device reset, and cross-device synchronization.

**Techniques:** Save a person’s explicit choices where technically supported; explain persistence and scope at the point of choice; keep an easy way to change or reset settings; avoid silently sharing a preference across people or devices; do not override a saved opt-out with a default on a later launch; distinguish personal settings from shared-room settings.

**Intended individual outcome:** A person does not need to repeat setup unnecessarily and can predict which settings will follow them, remain on a device, or affect other viewers.

**Evidence limits:** A documented persistence feature may apply only to selected settings or products. Verify behaviour; do not infer a profile model from a remembered setting.

**Sources:** S02, S12, S18–S21; design synthesis.

### F12. Synchronized second-screen access and control

**Status:** Historical prototype or project reference; design recommendation.

**Documented coverage:** A 3Cat/EBU project presentation describes synchronized personal accessibility devices with a TV and HbbTV media synchronization; demonstrations include personal-device presentation and alternative experience routes. A BBC research project describes a synchronized client/device-control concept. (S27–S31)

**Design approach:** Allow an individual to use a personal device for a preferred interface or synchronized access route while the shared television experience continues for others, where content rights, platform capabilities, and user choice permit.

**Method:** Pair the personal device with the television session; synchronize its relevant state to the media timeline; retain explicit user control over pairing, output, and disconnect. Test pause, seek, live delay, buffering, app suspension, network loss, device rotation, and recovery.

**Techniques:** Use a defined synchronization reference such as media time or playhead position; detect and correct drift after seek or interruption; communicate sync state and errors; make pairing and unlinking clear; allow the person to select private-device output and independent display settings; avoid assuming a phone is available or suitable; preserve an accessible TV-only route. Keep programme access-service creation and delivery in their specialist repositories.

**Intended individual outcome:** A person can use a synchronized personal screen for an individual access experience without losing their place in the shared programme or requiring others to adopt the same presentation.

**Evidence limits:** The cited work includes research and project demonstrations, not proof of a universal, standardised, or widely deployed feature. Synchronization performance, device interoperability, content rights, and service support must be verified for each implementation.

**Sources:** S27–S31.

### F13. Semantic control interface with state and secure pairing

**Status:** Historical prototype or project reference; design recommendation.

**Documented coverage:** The BBC Universal Control API slide deck and 2011 working papers describe an experimental architecture for clients to control TV/STB functions and obtain state or metadata. They are historical research sources, not current standards or evidence of deployment. (S30–S33)

**Design approach:** Where external control is supported, expose meaningful actions and system state so accessible clients can present controls in a way suited to the person. Avoid requiring a client to imitate a sequence of opaque remote key presses when a semantic action and state response can be provided.

**Method:** Define an access-controlled interface for discovering supported actions, requesting an action, receiving current state, and handling asynchronous results. Document capability, permissions, errors, and versioning.

**Techniques:** Expose semantic actions such as select, play, pause, seek, change volume, and select available interface settings; return meaningful state and error information; make client and TV pairing explicit, authenticated, revocable, and limited to necessary permissions; protect profile, viewing, and accessibility-preference data; reject stale or unauthorised commands; retain direct accessible controls when a connected client is unavailable.

**Intended individual outcome:** A person can use a compatible accessible client to control supported TV functions with feedback about what happened, while retaining control over privacy and connection.

**Evidence limits:** The cited API documents are experimental and from 2011. They do not establish a current interoperable API or deployed product feature. Treat the architecture as a design prompt only; check current standards, security needs, and product capabilities before implementation.

**Sources:** S30–S33.

## Cross-feature evaluation

Evaluate the complete task, not just whether a setting or control exists. Include realistic tasks such as completing first-run setup, finding a programme, switching between list and grid views, checking access-service availability, enabling or disabling a service, changing a preference, controlling playback from an alternative device, and recovering after synchronization or connection loss.

Record the exact device, model, software, region, app, programme/version, input and output methods, environment, task result, assistance required, observed focus or speech state, and participant-reported experience. Involve disabled people who use the relevant methods. Do not treat a support page, standards mapping, automated scan, synthetic persona, or agent review as user evidence or as proof of accessibility.

Use the repository’s [Connected TV](Connected_TV.md), [Accessible Interactive Media Control](Accessible_Interactive_Media_Control.md), and [Physical and Connected Product Control](Physical_and_Connected_Product_Control.md) guides for broader journey-level evaluation. Use [Inclusive Multimodal UX](https://github.com/Double-FW/Inclusive-Multimodal-UX) for general modality and semantic-structure guidance, [Cognitive UX Design](https://github.com/Double-FW/Cognitive-UX-Design) for cognitive access, and [QA Accessibility Testing](https://github.com/Double-FW/QA_Accessibility_Testing) for test design and evidence handling.

## Source register

Source URLs are listed here rather than beside individual feature descriptions. Vendor pages are support documentation and may be updated or vary by region and product. Check the applicable page and actual device before relying on a feature claim.

### Apple

- **S01 — Apple TV accessibility features:** https://support.apple.com/en-gb/guide/tv/atvbaeff85db/tvos
- **S02 — Accessibility settings in the Apple TV app:** https://support.apple.com/en-gb/guide/tvapp/atvbaeff85db/web

### Android TV, Sony, Panasonic, and Samsung

- **S03 — Android TV accessibility:** https://developer.android.com/training/tv/accessibility
- **S04 — Android TV system caption settings:** https://developer.android.com/training/tv/accessibility/system-caption-settings
- **S05 — Sony BRAVIA TV accessibility:** https://www.sony.co.uk/bravia/tv-accessibility
- **S06 — Sony BRAVIA accessibility overview:** https://www.sony.co.uk/bravia/tv-accessibility/bravia-accessibility
- **S07 — Sony model-specific accessibility shortcuts:** https://www.sony.co.uk/electronics/support/televisions-projectors-monitors/articles/00254823
- **S08 — Panasonic voice guidance: switch on or off:** https://help.na.panasonic.com/answers/how-to-turn-voice-guidance-on-or-off-television/
- **S09 — Panasonic voice guidance use and settings:** https://help.na.panasonic.com/answers/how-to-use-the-voice-guidance-function/
- **S10 — Samsung TV audio accessibility:** https://www.samsung.com/uk/sustainability/accessibility/tv-audio/
- **S11 — Samsung TV accessibility support:** https://www.samsung.com/uk/support/tv-audio-video/how-to-use-accessibility-features-on-my-samsung-smart-tv/

### Freeview, BT/YouView, and Sky

- **S12 — Freeview Accessible TV Guide:** https://www.freeview.co.uk/555
- **S13 — Freeview Accessible TV Guide device support:** https://www.freeview.co.uk/help/accessible-tv-guide
- **S14 — Freeview guide views and navigation:** https://www.freeview.co.uk/help/access-tv-guide
- **S15 — BT TV accessibility options:** https://www.bt.com/help/tv/getting-started-with-tv/accessibility-options-on-bt-tv
- **S16 — Sky accessibility remotes:** https://www.sky.com/help/articles/accessibility-remotes
- **S17 — Sky remote accessibility button explanations:** https://www.sky.com/help/articles/q-buttons-explained-access
- **S18 — Sky Q accessibility settings:** https://www.sky.com/help/accessibility-information/accessibility-settings-sky-tv/sky-q-accessibility/articles/using-the-accessibility-settings-on-your-sky-q-box
- **S19 — Sky Glass accessibility settings:** https://www.sky.com/help/accessibility-information/accessibility-settings-sky-tv/sky-glass-accessibility/articles/accessibility-settings-sky-glass
- **S20 — Sky Stream accessibility settings:** https://www.sky.com/help/accessibility-information/accessibility-settings-sky-tv/sky-stream-accessibility/articles/accessibility-settings-sky-stream
- **S21 — Sky+ accessibility setup:** https://www.sky.com/help/accessibility-information/accessibility-settings-sky-tv/sky-plus-accessibility/articles/set-up-sky-tv-accessibility-settings-in-your-sky-guide
- **S22 — Sky remote app:** https://www.sky.com/help/articles/sky-remote-app

### BBC iPlayer

- **S23 — BBC iPlayer accessibility:** https://www.bbc.co.uk/iplayer/help/questions/accessibility
- **S24 — BBC iPlayer subtitles:** https://www.bbc.co.uk/iplayer/help/questions/accessibility/using-subtitles

The BBC iPlayer pages were supplied as in-scope sources but could not be independently inspected by the research tooling used for this revision. No feature claims in this reference rely on them; consult the pages directly before using them to support a product-specific statement.

### Ofcom and EBU / project research

- **S25 — Ofcom Electronic Programme Guide Accessibility Report:** https://www.ofcom.org.uk/tv-radio-and-on-demand/accessibility/electronic-programme-guide-accessibility-report
- **S26 — Ofcom guidelines on providing TV and on-demand access services:** https://www.ofcom.org.uk/siteassets/resources/documents/tv-radio-and-on-demand/broadcast-codes/other-codes/ofcoms-guidelines-on-providing-tv-on-demand-access-services.pdf?v=357066
- **S27 — EBU/3Cat synchronized accessibility media presentation (2026, supplied PDF):** https://www.ebu.ch/files/live/sites/ebu/files/Groups/Media/Access%20Services/2026_slides/3cat_ascm_sync_devices.pdf
- **S28 — 3Cat Universal HbbTV MediaSync project:** https://github.com/CCMA-Enginyeria/Universal-HbbTV-MediaSync-App
- **S29 — 3Cat Universal HbbTV MediaSync demonstration:** https://ccma-enginyeria.github.io/Universal-HbbTV-MediaSync-App/
- **S30 — BBC Universal Control API presentation (2011):** https://www.w3.org/2010/11/web-and-tv/slides/BBC-Universal-Control-API.pdf
- **S31 — BBC WHP194, Universal Control API version 0.6.0 (2011, supplied PDF):** https://downloads.bbc.co.uk/rd/pubs/whp/whp-pdf-files/WHP194.pdf
- **S32 — BBC WHP193, Universal Control API overview (2011):** https://downloads.bbc.co.uk/rd/pubs/whp/whp-pdf-files/WHP193.pdf
- **S33 — W3C Web and TV / Universal Control API historical context:** https://www.w3.org/2010/11/web-and-tv/

The 3Cat/EBU and BBC materials describe project demonstrations or historical research architectures. They are useful for design questions about synchronization and semantic control, but do not establish a current universal standard or broad product deployment.
