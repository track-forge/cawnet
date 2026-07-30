# Open questions and prototype parameters

CAWNET is deliberately not choosing hardware yet. These questions define what
we should observe, measure, or decide before a prototype stack hardens.

## Experience

- What does a CAW mean to the crew, and when do people naturally send one?
- Which feedback combination works in wind, helmets, trees, conversation, and
  quiet places: audio, haptic, light, or several?
- How should the ca-caw sound avoid wildlife confusion and trail annoyance?
- What feedback confirms a local button press versus remote receipt?
- What latency still feels immediate?
- How do people join, leave, and identify a temporary crew without a screen?
- Is one signal enough, or would additional messages dilute the simplicity?

## Physical design

- What is the total acceptable weight for a pole-top button?
- Is “a couple ounces” acceptable for the separate wraparound sensor, and what
  is the real target after field trials?
- Where on different pole grips can a gloved thumb reliably find the control?
- Adhesive, elastic strap, silicone wrap, mechanical clamp, or an integrated
  grip: which attachment survives cold, water, impacts, and pole baskets?
- Can the attachment avoid changing swing weight or snagging straps?
- What ingress, impact, cold, UV, and freeze/thaw requirements are realistic?
- How are battery access, charging, and wet connectors handled?
- Which alternate mounts make the same interaction work on a mountain bike,
  backpack strap, jacket, or vehicle?

## Range and topology

- What useful range is needed in dense trees, gullies, open slopes, and a
  parking lot?
- Is the desired network direct device-to-device, personal hub-and-spoke,
  relayed, mesh-like, or adaptive?
- How many people and devices make up a normal and maximum crew?
- How should duplicates, collisions, partitions, reconnection, and relay loops
  behave?
- Is cross-crew isolation desirable when several groups are nearby?
- How should degraded range or an unreachable peer be communicated without
  suggesting danger?

## Radio and regulation

- Which candidate technologies merit testing: BLE, LoRa or other sub-GHz radio,
  proprietary low-power links, Wi-Fi variants, or combinations?
- What regional spectrum rules, duty cycles, transmit-power limits,
  certifications, and labeling apply?
- How much interference should be expected from phones, radios, resort systems,
  vehicles, and other CAWNET crews?
- Does audio signaling create separate trail, wildlife, or venue constraints?

## Power and compute

- What runtime is required: one outing, a weekend, or a season of standby?
- Replaceable primary cell, rechargeable cell, supercapacitor, or another power
  model?
- What happens to battery performance in deep cold?
- What standby draw and transmit budget follow from realistic CAW frequency?
- Can the minimal button work independently of the backpack node?
- What workload, if any, justifies SBC-class compute and its weight, boot time,
  fragility, and power cost?
- Is solar or motion harvesting useful, or merely complexity?

## Audio and sensing

- How loud must a ca-caw be near wind and helmets, and where can a speaker live?
- Would bone conduction, haptics, or a piezo be more effective?
- Should volume be automatic, configurable, or socially constrained?
- Which sensors create an actually delightful feature rather than data exhaust?
- Does motion sensing belong on the pole, in the backpack, or nowhere?
- What data is ephemeral, and what—if anything—is stored locally?

## Security and privacy

- How does a temporary crew establish trust with minimal setup?
- Can strangers spam, replay, spoof, track, or fingerprint CAWs?
- Should messages be authenticated or encrypted, and what user experience does
  key exchange require?
- What identifiers rotate, and how quickly?
- What diagnostics exist without storing coordinates or a durable movement
  history?
- How are lost or borrowed devices removed from a crew?

## Firmware and maintenance

- How are firmware updates performed without making a phone or cloud account
  mandatory for ordinary use?
- What is the recovery path after a failed update?
- What physical debug interface is appropriate for Grapple Probe and field
  service?
- Which health checks can a user perform before heading out?
- How do hardware revisions remain interoperable?

## Cost and buildability

- What bill-of-materials target makes a crew-sized kit approachable?
- Which parts dominate cost, weight, enclosure volume, and lead time?
- Should the first kit be assembled, a DIY build, or both?
- Which parts need certification or specialized manufacturing?
- How repairable should each form factor be?
- Which software, firmware, hardware, documentation, brand, and asset licenses
  fit the project? Licensing remains TBD until that is decided intentionally.

## First evidence to collect

Before selecting a platform, useful early work could include:

1. Field interviews and a paper/mock enclosure test with ski gloves.
2. Weight and attachment experiments on several pole grips and shafts.
3. Sound and haptic perception tests in representative outdoor conditions.
4. A written message-state model separating local press, device receipt, and
   human meaning.
5. Candidate-radio range and power test plans based on measured terrain needs.
6. A safety-language review to keep the product firmly in the stoke lane.

