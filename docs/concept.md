# CAWNET concept note

## Purpose

CAWNET — the **Backcountry Acknowledgment Network** — gives a nearby crew a
lightweight way to say “I am here, I heard you, this rules” through a shared
CAW.

It is a social signal for outdoor motion: an avalanche beacon for STOKE, and
explicitly not a safety or rescue system.

## Core moment

1. A skier presses the single button on a pole-top node.
2. Their device gives immediate local feedback that the press registered.
3. Nearby crew devices receive a CAW.
4. Receiving devices answer with a recognizable ca-caw through audio, haptics,
   light, or some combination.
5. The crew keeps moving. No phone screen or cloud round trip is required.

The exact acknowledgment semantics are still open. The system must distinguish
“my button registered,” “a device heard the message,” and “a human is okay.”
Only the first two can be technical claims, and neither implies the third.

## Conceptual roles

These are product roles, not hardware specifications. A device may fill more
than one role.

### CAW button

The smallest, most immediate device. It sends a CAW and provides enough feedback
to confirm the local interaction. Its design priorities are gloved use, low
weight, robust attachment, cold-weather power, and simplicity.

### Companion sensor

An optional wraparound pole module that adds sensing without making the button
bulky. Motion, temperature, or other measurements may be interesting, but no
sensor feature is assumed to be necessary.

### Backpack node

A larger personal node that can support stronger audio, a larger battery, more
compute, storage for non-sensitive local state, or relay behavior. It might use
microcontroller-class or SBC-class hardware; that choice follows power and
experience requirements. It could also act as an optional WAN gateway, although
a phone may be the lighter and more practical backhaul. Neither is required for
local operation.

### Crew relay

An optional node that helps CAWs move through a small ad-hoc crew network.
Relaying may be useful, but it also creates latency, duplication, power,
security, and user-expectation questions.

### Base or trailhead node

A vehicle, hut, or trailhead form factor could provide louder feedback,
charging, diagnostics, or playful group interactions. It must not imply
monitoring or rescue coverage.

## Conceptual messages

- **CAW** — the primary user-generated stoke signal.
- **Heard** — a protocol-level acknowledgment that one or more devices received
  a CAW. It never means a person is safe.
- **Crew hello** — local discovery or presence for forming a temporary crew.
- **Personal CAW** — a compact authenticated identity/event that lets a
  receiving device play the sender's chosen local sound.
- **Status** — optional device health such as low battery or link quality,
  presented without implying emergency reliability.
- **Test CAW** — an explicit pre-activity check that exercises feedback and
  teaches the interaction.
- **Extended-crew presence** — an explicitly enabled, expiring indication that
  a person or crew is around, optionally including coarse or exact location.
- **Area activity** — a private, expiring indication that a trusted crew has
  already skied an area or line.

Names, payloads, and whether every message should exist remain open.

## Network shape

The working mental model has two overlapping layers:

- a **personal area network** connecting a person's button, sensor, and backpack
  node; and
- an **ad-hoc crew network** exchanging CAWs among nearby people.

A third, optional layer could use phone or backpack-node backhaul to connect
selected extended crews over the WAN. It is an augmentation, not a prerequisite
or fallback safety channel. Network loss must leave the PAN and nearby CAW
experience usable.

This does not select BLE, LoRa, mesh routing, a star topology, store-and-forward,
or any other implementation. “Mesh” is a user-facing ambition to explore, not
a promise that every node routes every packet.

## Personal audio identity

A personal CAW could make the sender recognizable without looking at a screen:
raven, eagle, wood thrush, a short guitar lick, or another chosen sound.
Recipients need quiet and haptic-only modes, volume controls, and a clear way to
identify a sender when sound is muted.

A likely efficient design is to transmit a compact authenticated identity/event
and play a cached sound on the receiving node rather than streaming audio over
the low-power mesh. WAN provisioning or direct sync could distribute sound
packs ahead of time. Sound length, storage, transcoding, licensing, offensive
content, impersonation, and moderation all remain open product questions; this
paragraph does not select a protocol or architecture.

## Optional extended-crew layer

With explicit user consent, a WAN-connected tier could help friends moving in
different crews discover that they are both out and arrange a rendezvous. The
sharing control should make three choices plain:

- **precision** — presence only, a coarse area, or exact location;
- **audience** — named people or selected crew access-control lists, never the
  general public;
- **expiry** — a short, visible time-to-live rather than an indefinite setting.

Trusted friends could also share expiring “we skied this area/line” activity so
another crew can target different terrain. Stash and line information is
especially sensitive: an area-level indication may often be more appropriate
than a named line or track, and sharing must never silently become a public map
or durable route history.

These features are social coordination, not tracking or rescue features.
Presence may be stale, delayed, imprecise, revoked, or unavailable.

## Privacy direction

The direction is local-first and private by default:

- core use works without the cloud;
- no account is required;
- coordinates are not stored or shared by default;
- crew association is temporary and understandable;
- messages expose as little identifying information as practical;
- logs and diagnostics are bounded, visible, and erasable.
- WAN presence, location, and area activity are opt-in, audience-scoped,
  time-bounded, revocable, encrypted, and never public or retained as default
  history;
- crew access changes and lost devices take effect quickly;
- product design accounts for metadata leakage even when message contents are
  encrypted.

Any location prototype requires a specific privacy, abuse, and safety review
before field use. Encryption alone does not hide timing, traffic volume,
relationships, IP-level information, or every location inference.

## Non-goals

- emergency communications, search and rescue, or avalanche locating;
- continuous person tracking, default route recording, or public location
  history;
- social feeds, engagement metrics, or mandatory cloud accounts for core use;
- replacing a phone, radio, satellite messenger, or certified beacon;
- selecting a protocol or hardware bill of materials before field constraints
  are understood;
- maximizing range at the expense of weight, power, legality, or a clear user
  experience;
- turning a joyful one-button object into a screen-heavy general-purpose
  computer.

## Collaboration and tools

Grapple Systems and Grapple Probe could help make the exploratory hardware
pleasant to debug: SWD/JTAG, UART, radio behavior, sensors, battery systems, and
isolated field connections are all plausible areas. CAWNET may also be useful
as a reference project for field-debug workflows. No collaboration terms,
interfaces, or products are committed yet.
