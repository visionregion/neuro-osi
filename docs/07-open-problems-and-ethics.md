# 7. Open Problems & Ethics

[← Augmented Reality](06-augmented-reality.md) · [Next: Glossary →](08-glossary.md)

Neuro-OSI is a framework for discussion, not a solution. These are the problems it does not solve, and the ethical questions it raises.

## Open technical problems

### 1. Semantic incompatibility
There is no universal neural code. Layer 6 will require individual calibration for every person and, most likely, an AI translator in the middle. This creates a new point of trust: the translator sees everything. How can translation be done without a trusted intermediary? Possible directions: on-device translation, homomorphic or privacy-preserving computation, open and auditable codecs.

### 2. Latency and energy
Implants have a very limited power budget. On-device inspection of traffic (NGFW, DLP, AI Guardian) is expensive. The security stack must be designed for extreme efficiency, possibly with dedicated low-power security hardware.

### 3. Defining "intent"
Intent gating assumes it is possible to reliably distinguish a deliberate thought from an involuntary one. This is a hard neuroscience problem, and an error in either direction is costly: false negatives leak private thoughts, false positives silence the person.

### 4. Source attribution in perception
Can a foreign thought be marked in a way that the brain reliably perceives as foreign, for years, without habituation? This is an open question for neuroscience and human-computer interaction.

### 5. Updates without risk
A firmware or AI model update to a brain implant is a high-stakes operation. Rollback, staged deployment and independent verification are mandatory, but the details are unsolved.

## Ethical questions

### Who controls the firewall?
A tool that filters thoughts is also the perfect tool for censorship. Neuro-OSI's fundamental requirement: **firewall and DLP policies are controlled by the person only**, and the logic runs locally on the implant, not in a cloud.

### Corporate and state access
Employers, insurers, law enforcement and governments will all have reasons to want access to neural data. Neuro-OSI assumes that neural data belongs exclusively to the person, and that no legitimate interest justifies bypassing their consent.

### Consent of third parties
Bystanders in AR, people present in shared memories, and recipients of group broadcasts all have rights that need protection.

### Mental integrity
Even a perfectly secure system can be used to influence people through consented but manipulative content. Security is necessary but not sufficient; ethics of design matter.

### Unequal access
If neural communication offers real advantages, unequal access to it may deepen social inequality.

## Legal landscape

The idea of **neurorights** is already entering law:

- **Chile** (2021) amended its constitution to protect mental integrity and brain data, becoming the first country to do so.
- **Colorado** (2024) and **California** (2024) included neural data in the category of sensitive personal data in their privacy laws.
- International organizations have begun work on ethical frameworks for neurotechnology.

Neuro-OSI aims to complement legal protection with **technical protection by design**: rights mean little if the architecture makes violating them easy.

## Possible next steps

- A detailed **handshake protocol** for Layer 5 (an analogue of TLS 1.3 with explicit consent).
- A **threat model** based on STRIDE for each layer.
- A more detailed **NGFW policy matrix** for typical roles: family, work, doctor, state.
- A conceptual **RFC: "Neural Transport Protocol"**.

Contributions in any of these directions are welcome. See [CONTRIBUTING.md](../CONTRIBUTING.md).
