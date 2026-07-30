# CAWNET

**The Backcountry Acknowledgment Network**

CAWNET is an idea for wearable electronics that let a crew exchange a simple,
joyful signal outdoors: **CAW!**

The shortest description is **an avalanche beacon for STOKE**. That phrase is
about the social feel, not the function. CAWNET is not avalanche equipment,
rescue equipment, a locator, or a substitute for radios, partner protocols,
training, judgment, or any certified safety device.

## The spark

Imagine a tiny one-button unit at the top of a ski pole. Press it with a glove
and your nearby crew hears a ca-caw acknowledgment. The same core interaction
could live on a mountain-bike bar, a backpack strap, or another outdoor
attachment.

Around that simple button, CAWNET could grow into a personal area network (PAN)
and a small ad-hoc crew network:

- a tiny pole-top button, attached with adhesive, a strap, or another
  field-friendly mount;
- an optional lightweight sensor module wrapped around the pole, inspired by
  the rubber-cased Garmin hub speed sensor;
- a richer backpack node with more battery, compute, audio, and possibly
  SBC-class hardware;
- crew-to-crew CAW messages with audible, haptic, or visual acknowledgments.

The button is the heart of it. Everything else is optional.

An optional WAN-connected tier could extend that local experience beyond the
nearby crew. When a user deliberately enables it, selected friends in other
crews could see a time-bounded presence or location and rendezvous on the hill.
Trusted crews might also privately share which areas or lines they have already
skied so friends can aim for another stash. This tier must remain optional,
audience-scoped, revocable, and ephemeral; core CAWs continue to work without a
phone, account, Internet connection, or cloud service.

Each person could also choose a recognizable personal CAW: a raven, eagle,
wood-thrush, guitar lick, or another short sound. One efficient possibility is
to send a compact authenticated identity/event over the low-power network and
play the recipient's cached sound locally, with optional WAN provisioning for
sound packs. That is a concept to test, not an implementation decision.

## Project status

CAWNET is in the **idea and creative phase**. This repository is for product
notes, field questions, sketches, and experiments in definition. There is no
implementation yet.

No radio, processor, battery, topology, or hardware platform has been selected.
LoRa, BLE, and other approaches are possibilities to investigate, not
decisions.

## Product principles

- **One obvious interaction.** A gloved person should be able to send a CAW
  without looking at a screen.
- **Tiny where it matters.** The pole-top unit should feel like part of the pole,
  not a gadget dangling from it.
- **Joy, not false confidence.** CAWNET communicates acknowledgment and stoke,
  never a claim of safety, rescue readiness, or reliable location.
- **Local-first and private by default.** Start with no cloud dependency, no
  stored coordinates by default, and no account required for the core
  interaction. WAN sharing is a deliberate, temporary opt-in.
- **People control their visibility.** Presence and location sharing require a
  chosen audience, precision, and expiry, and can be revoked at any time.
- **Crew-scale.** Optimize for people moving together nearby, while leaving the
  useful range and network shape open to evidence.
- **Modular form factors.** Reuse the interaction across skiing, mountain
  biking, and other activities without forcing one enclosure everywhere.
- **Weather and gloves are first-class constraints.** Snow, cold, water,
  impacts, and clumsy hands are the actual interface.
- **Delight is functional.** The ca-caw should be recognizable, satisfying, and
  socially legible without becoming obnoxious.
- **No premature hardware lock-in.** Learn the parameters before choosing the
  stack.

## Candidate form factors

1. **Pole-top CAW button** — the smallest expression: one button, minimal
   feedback, and an adhesive or strap-style attachment.
2. **Wraparound pole sensor** — a separate couple-ounce-or-less target module
   that hugs the shaft in a protective rubber-like carrier and can host motion
   or environmental sensing.
3. **Backpack node** — room for a larger battery, stronger audio, richer
   feedback, local relay behavior, optional WAN gateway/backhaul, and more
   compute. An SBC is possible but intentionally undecided.
4. **Activity mounts** — alternate housings for a mountain-bike handlebar,
   backpack strap, jacket, vehicle, or trailhead installation.

See [the concept note](docs/concept.md) for roles and message ideas, and
[open questions](docs/open-questions.md) for the parameters we need to learn.

## Grapple Systems connection

CAWNET is a natural embedded-systems playground for Grapple Systems and Grapple
Probe: debugging firmware, radios, sensors, power systems, and the strange
ground problems that appear when wet outdoor electronics meet bench equipment.
Possible collaboration includes field-debug interfaces, power architecture,
and test fixtures. That relationship is exploratory, not a committed
architecture or vendor choice.

## Safety boundary

CAWNET must never be marketed, documented, or represented as:

- an avalanche transceiver or beacon;
- a personal locator beacon, satellite messenger, or emergency communicator;
- a dependable way to find a person;
- a replacement for radios, rescue equipment, training, travel protocols, or
  judgment;
- a guarantee that a message was received or that another person is safe.

Future prototypes should make failure visible and avoid interaction language
that could be confused with an emergency acknowledgment.

## Contributing ideas

Bring field stories, sketches, constraints, weird mounts, and testable
questions. At this stage, a good contribution helps define the experience or
turns an assumption into something measurable. Please avoid implementation PRs
until the basic parameters and an initial prototype brief are agreed.

## Licensing

Licensing is **TBD**. This repository intentionally has no license while we
decide how software, firmware, hardware designs, documentation, branding, and
creative assets should be licensed.
