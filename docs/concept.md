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
experience requirements.

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
- **Status** — optional device health such as low battery or link quality,
  presented without implying emergency reliability.
- **Test CAW** — an explicit pre-activity check that exercises feedback and
  teaches the interaction.

Names, payloads, and whether every message should exist remain open.

## Network shape

The working mental model has two overlapping layers:

- a **personal area network** connecting a person's button, sensor, and backpack
  node; and
- an **ad-hoc crew network** exchanging CAWs among nearby people.

This does not select BLE, LoRa, mesh routing, a star topology, store-and-forward,
or any other implementation. “Mesh” is a user-facing ambition to explore, not
a promise that every node routes every packet.

## Privacy direction

The initial direction is local-first:

- core use works without the cloud;
- no account is required;
- coordinates are not stored;
- crew association is temporary and understandable;
- messages expose as little identifying information as practical;
- logs and diagnostics are bounded, visible, and erasable.

Location features are outside the initial concept. Adding them later would
require an explicit product, privacy, and safety review.

## Non-goals

- emergency communications, search and rescue, or avalanche locating;
- continuous person tracking or route recording;
- social feeds, engagement metrics, or cloud accounts;
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

