---
title: "Agent Guidance: Inclusive Media Interfaces"
version: "1.0.0"
author: "Double FW"
date: "2026-11-23"
license: "MIT"
language: "en-GB"
repository: "https://github.com/Double-FW/Inclusive-Media-Interfaces"
artifact_type: "agent-governance"
use_case: "Guide AI-assisted retrieval, design analysis, research planning, review, and maintenance of media-interface guidance."
status: "active"
review:
  status: "owner_review_required"
  owner: "Repository maintainer"
  trusted_for_agent_use: "after_owner_review"
license_source: "LICENSE"
conceptual_entities:
  task_context: "A person's media task, interface, device, software, environment, access methods, and constraints."
  access_service: "A feature such as captions, subtitles, audio description, signing, or spoken interface support."
  evidence: "Sourced or observed information distinguished from report, interpretation, inference, hypothesis, and synthetic material."
  design_decision: "A human-owned choice with rationale, evidence limits, trade-offs, and follow-up."
agent_policy:
  required:
    - "Read README.md and the relevant guide before making repository-specific claims."
    - "Use terminology according to the scope and status recorded in Terminology and Principles."
    - "Keep source guidance, participant reports, observed behaviour, technical inspection, inference, hypotheses, and synthetic material distinct."
    - "Do not infer one modality preference for a disability group or treat an access-service listing as proof of usable access."
    - "Route detailed questions to the owning public Double-FW source."
    - "State assumptions, uncertainty, evidence limits, and what could change the recommendation."
  human_authorization_required:
    - "Contact participants, deploy research, or run live-user experiments."
    - "Access or publish identifiable or sensitive customer/research data."
    - "Change a live product, make a consequential product decision, or make a legal/conformance claim."
---

# Agent Guidance: Inclusive Media Interfaces

## Purpose and authority

Use this repository for television, streaming, playback, media access services, and physical or connected controls that support media access. It is practitioner guidance, not a legal assessment, conformance result, or substitute for research with people.

Keep these areas distinct and route to the owning source: media-interface design; media content production; caption/subtitle authoring; general modality principles; and regulatory interpretation.

## Required context

Before a specific recommendation, identify or request:

- the service, interface, device, player, remote, and software version where known;
- the person’s goal, task, environment, and relevant constraints;
- available access services and the content or media version;
- available input and output methods; and
- whether the question concerns discovery, setup, interface control, physical hardware, environmental control, content production, captioning, or regulatory evidence.

Do not invent missing details. Label assumptions and state what needs verification.

## Source routing

Retrieve the most specific guide, then follow relevant cross-links:

- TV setup, navigation, remote use, access-service discovery, and spoken output: [Connected_TV.md](Connected_TV.md).
- Cross-platform TV feature comparisons, documented examples, implementation recommendations, and their evidence limits: [TV_Accessibility_Feature_Reference.md](TV_Accessibility_Feature_Reference.md).
- Media-specific input flexibility, cognitive demand, feedback, control, and agency: [Accessible_Interactive_Media_Control.md](Accessible_Interactive_Media_Control.md).
- Custom web video player controls, semantics, keyboard and assistive input, playback feedback, and review: [Accessible_Web_Video_Player_Controls.md](Accessible_Web_Video_Player_Controls.md).
- Physical controls, shared spaces, environmental control, hardware integration, and connected-product ecosystems: [Physical_and_Connected_Product_Control.md](Physical_and_Connected_Product_Control.md).
- General modality choice, transitions, and semantic structure: [Inclusive Multimodal UX](https://github.com/Double-FW/Inclusive-Multimodal-UX).
- Accessible media planning and production: [Accessible Film, TV and Video Content Production Management](https://github.com/Double-FW/Accessible-Film-TV-and-Video-Content-Production-Management).
- Caption and subtitle authoring/delivery: [Closed Caption Subtitles](https://github.com/Double-FW/Closed-Caption-Subtitles).
- Games-specific interaction: [Inclusive Games Design](https://github.com/Double-FW/Inclusive-Games-Design).
- Regulatory requirements and evidence: [AVMSD](https://github.com/Double-FW/The-Audiovisual-Media-Services-Directive-AVMSD-) and the applicable legal specialist.
- Terminology: [Terminology and Principles](https://github.com/Double-FW/Terminology-and-Principles), beginning with [START_HERE.md](https://github.com/Double-FW/Terminology-and-Principles/blob/main/START_HERE.md).

Do not copy a complete specialist guide into this repository. Keep cross-links pointed to public repositories and verify any linked file path.

## Review method

For a relevant journey:

1. Define the goal, task, stakes, and context.
2. Check discovery and setup, including whether the person can configure the device and find content, access services, and settings. Use the TV feature reference to distinguish documented platform examples from design recommendations; verify exact model and software before making product claims.
3. Check controls, input methods, focus/selection, state, consequences, and feedback.
4. Check continuity of context and preferences across content, sessions, and devices; do not assume persistence without user control.
5. Check interruption, error, correction, exit, and recovery.
6. Consider viewing distance, lighting, noise, fatigue, time pressure, shared use, and connectivity without assuming the same effects for everyone.
7. For connected systems, consider interoperability, maintainability, privacy, and security.
8. Recommend a useful next step and identify evidence needed to evaluate it.

## Evidence and terminology

- Consult the relevant term entry and its current review status. Approval of selected terminology decisions is not blanket approval of every glossary entry.
- Preserve distinctions between user, customer, and participant; access need and preference; observation, interpretation, estimate, and hypothesis; and comparable and equivalent.
- State what is being compared. Do not claim equivalence without a defined criterion and evidence that supports it.
- Distinguish access-service availability from discoverability, selection, activation, and successful use.
- Do not treat synthetic personas, generated scenarios, automated scans, simulated tasks, or agent reasoning as research with disabled people.
- Preserve negative, minority, and contradictory evidence; do not average away serious barriers.
- Do not claim legal applicability, compliance, or conformance without appropriate evidence and accountable human review.

## Human authority, privacy, and maintenance

Agents may retrieve sources, frame questions, draft options, and analyse evidence supplied for the task. A human must authorise participant contact, research deployment, live-user experiments, access to identifiable or sensitive data, production changes, acceptance of material risk, and publication of consequential claims.

Keep personal data, credentials, identifiable customer records, raw recordings, and transcripts out of this public repository. Minimise and de-identify evidence; refer to approved access-controlled storage where needed.

Preserve provenance, attribution, and source-specific licence terms. The repository’s MIT licence does not relicense linked or quoted content. Before editing, check for public links, resolved paths, duplication, contradictions, unsupported causal or universal claims, and accidental truncation. Keep audit and test reports out of the repository unless explicitly requested.
