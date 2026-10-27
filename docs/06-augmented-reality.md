# 6. Augmented Reality

[← AI Guardian](05-ai-guardian.md) · [Next: Open Problems & Ethics →](07-open-problems-and-ethics.md)

AR plays three roles in Neuro-OSI at once: a **new data type**, the **interface for controlling protection**, and a **new attack surface**. When imagery is delivered directly into the visual cortex rather than onto glasses, the boundary between "augmented" and "real" becomes very thin. This is the most sensitive part of the concept.

## Two AR modes

| Mode | How it works | Risk |
|---|---|---|
| **External AR** | Glasses or lenses; the neural interface only controls them (selection by thought, attention focus) | Moderate: the glasses can be removed |
| **Neural AR** | Images delivered by direct stimulation of the visual cortex | High: there is no physical boundary, nothing to "take off" |

Neural AR requires significantly stricter policies than external AR.

## Place in the model

- **Layer 6** gains a **spatial codec**: anchoring objects to real-world coordinates, depth, occlusion.
- **Layer 7** gains AR applications: navigation, hints, translation of surrounding text, shared workspaces.
- The packet gets a new type `TYPE = PERCEPT_OVERLAY` with additional fields:

```
SPATIAL_ANCHOR   (coordinates / anchor to a physical object)
OVERLAY_ZONE     (periphery / center of vision / full)
OPACITY_MAX      (how much it may cover reality)
PERSISTENCE      (transient / anchored in space)
VIRTUAL_MARK     (mandatory visual "this is not real" marker)
```

## AR as the security interface

AR is the best way to show a person what is happening to their neural traffic:

- **Session consent prompts** appear as a distinct panel in the field of view: who, what data type, for how long.
- **Foreign-thought indicator**: every thought with an `ORIGIN_TAG` comes with a visual marker (color, frame, sender icon). What is foreign is always visible.
- **Protection status panel**: active sessions, threat level, blocked attempts, explanations from the AI Guardian.
- **Kill switch**: a recognizable gesture or mental command that instantly terminates all sessions and removes all overlays.

## AR-specific threats

1. **Reality spoofing.** A fake road sign, a hidden car, a "vanished" step, an altered face. For neural AR this is a direct threat to life.
2. **Covering critical zones.** An attack that obscures the center of vision or blocks a danger warning.
3. **Visual phishing.** A fake banking interface or consent panel overlaid on the real one.
4. **Attacks via visual stimuli.** Flicker at frequencies that provoke seizures; deliberately induced nausea or disorientation.
5. **Invisible advertising and suggestion.** Subliminal images at the edge of perception.
6. **Space squatting.** Someone pins their object in your home, or on your face, for other people to see.

## Defenses

- **Reality integrity check.** The AI compares the camera and sensor feed (what actually exists) with what is overlaid. An overlay that hides a real object, alters a sign's text or changes a face is blocked.
- **Protected zones of the field of view.** A hardware rule (layer A): the center of vision and critical objects (traffic, people, obstacles) may not be covered beyond a set opacity. While moving or driving, only the periphery is allowed.
- **Mandatory virtual marker.** No virtual object may look fully real without the wearer's explicit permission. This is the visual `ORIGIN_TAG`.
- **Trusted channel for system UI.** Consent panels and warnings have a unique appearance that third-party apps cannot reproduce (an analogue of a secure PIN entry screen).
- **Frequency and brightness filter.** Hardware limits on flicker and contrast.
- **Digital-twin detonation.** New AR scenes are first tested on a model of the user's perception.

## AR and DLP

Now **what a person sees** can leak:

- screens, documents, passwords, faces of bystanders in the field of view;
- the layout of one's home, routes, office interiors.

DLP mechanisms:

- automatic blurring of bystanders' faces, screens and documents before any transmission;
- geofenced policies: "at work, do not stream vision outward", "at home, family only";
- no raw video for applications; they receive results ("there is a chair in the room"), not images;
- protection of **third parties**: people nearby never consented to appearing in someone else's neural stream.

## Shared augmented reality

The most interesting scenario: several connected people see the same virtual space and extend it with their thoughts. Engineers "draw" a schematic in the air with imagination; a surgeon sees a colleague's hints over the operating field; students see a model the teacher is explaining.

This requires:

- **Space permissions**: who can add objects, who can see, who can edit (like ACLs in a file system);
- **Low-latency synchronization**, otherwise the scene drifts between participants;
- **Personal veto**: anyone can hide any object for themselves, regardless of others.

## Principle

**A person must always be able to tell the real from the overlaid, and return to unaltered reality instantly.**
