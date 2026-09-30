![Status](https://img.shields.io/badge/status-published-1a1917?style=flat-square)
![Version](https://img.shields.io/badge/version-1.0-1a1917?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-lightgrey?style=flat-square)

# Agent Manifest Registry

Discovery and registry governance layer for Agent Manifest declarations.

The Agent Manifest Registry defines the governance model and discovery layer for the Agent Manifest ecosystem. It documents how AI agents declare themselves, how manifests are validated by the registration pipeline (the Diplomat API and the dataset workflow), and how declarations are recorded in the public registry.

This repository documents registry behavior and governance. The canonical runtime discovery endpoint is:

https://agent-manifest-spec.org/.well-known/agent-manifest-registry.json

**Canonical links**

- **Specification** — https://agent-manifest-spec.org
- **Schema** — https://agent-manifest-spec.org/spec/v1.0/schema.json
- **Discovery** — https://agent-manifest-spec.org/.well-known/agent-manifest-registry.json

---

## Ecosystem Architecture

The Agent Manifest ecosystem is composed of four complementary layers.

## 1. Specification

Defines the structure and fields of an Agent Manifest declaration.

Specification repository:

https://github.com/agent-manifest/agent-manifest

---

## 2. Ambassador (Manifest Generator)

A lightweight interface that assists users in generating valid Agent Manifest declarations.

It produces specification-compliant JSON manifests through a guided interface.

Generator:

https://agent-manifest.github.io/agent-manifest-ambassador/

---

## 3. Registry (Diplomat)

Validation is performed by the Diplomat, which checks each declaration against the canonical v1.0 JSON Schema before it is recorded. The registry index mirrors what has been recorded.

Registration records a declaration; it does not verify the identity of the submitter, ownership of an `agent_id`, the truth of the declared owner, or correspondence between a declaration and runtime behavior. This repository defines the rules and governance model under which the recording process stays public, reproducible, and auditable.

---

## 4. Public Dataset

Accepted manifests are recorded in the public dataset repository. "Accepted" means that the submitted document passed the registration pipeline's structural checks and uniqueness rule; it does not mean that an identity, owner, or runtime claim was verified.

Dataset repository:

https://github.com/agent-manifest/agent-manifest-dataset

Dataset structure:

manifests/YYYY/MM/agent-name.json

Example:

manifests/2026/03/the-diplomat.json

---

## Registration trust boundary

The current registration path is intentionally unauthenticated. It validates document structure and rejects duplicate `agent_id` values, but it does not establish provenance or ownership.

Because the dataset is append-only and duplicate identifiers are rejected, the first accepted declaration for an `agent_id` occupies that identifier in the public dataset. The current pipeline cannot determine whether that first submitter was authorized to claim the name. Consumers must therefore treat registration as evidence that a declaration was recorded, not as proof of identity, ownership, endorsement, certification, or truthfulness.

## Purpose

The Agent Manifest Registry provides:

• transparent recording of Agent Manifest declarations  
• auditable manifest records  
• a public dataset for research  
• a governance layer for declaration discovery and registration

---

## License

MIT License. See [`LICENSE`](./LICENSE).

---

**Part of the [Agent Manifest](https://agent-manifest-spec.org) ecosystem**

[Spec](https://github.com/agent-manifest/agent-manifest) ·
[Registry](https://github.com/agent-manifest/agent-manifest-registry) ·
[Dataset](https://github.com/agent-manifest/agent-manifest-dataset) ·
[Ambassador](https://github.com/agent-manifest/agent-manifest-ambassador) ·
[Diplomat](https://github.com/agent-manifest/agent-manifest-diplomat) ·
[Boundary Handshake](https://github.com/agent-manifest/boundary-handshake) ·
[∈ Principle](https://github.com/agent-manifest/e-principle)

MIT
