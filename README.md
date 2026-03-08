# Agent Manifest Registry

This repository provides the discovery endpoint for the Agent Manifest Public Registry.

Discovery endpoint:

https://raw.githubusercontent.com/hernancapucci/agent-manifest-registry/main/.well-known/agent-manifest-registry.json

The registry dataset is maintained in:

https://github.com/hernancapucci/agent-manifest-dataset

The specification is defined in:

https://github.com/hernancapucci/agent-manifest

The Agent Manifest Registry defines the rules, structure, and governance process for declaring AI agents using the Agent Manifest specification.

This repository serves as the institutional layer of the Agent Manifest ecosystem.

It defines:

• how agents declare themselves  
• how manifests are structured  
• how declarations are validated  
• how manifests are recorded in the public dataset

---

## Ecosystem Architecture

The Agent Manifest ecosystem is composed of four layers.

### Specification

The specification defines the structure of an Agent Manifest.

It describes the fields, schema and declaration model.

---

### Ambassador (Generator)

The Ambassador is a lightweight interface that helps generate valid manifests.

It guides users through a simple conversational flow and produces a valid JSON declaration.

Live generator:

https://hernancapucci.github.io/agent-manifest-ambassador/

---

### Diplomat (Registry)

The Diplomat acts as the registry process responsible for recording manifests into the public dataset.

It ensures that declarations follow the specification and are stored transparently.

---

### Dataset

All manifests are stored in the public dataset repository.

Dataset location:

https://github.com/hernancapucci/agent-manifest-dataset

Structure:

manifests/YYYY/MM/agent-name.json

Example:

manifests/2026/03/the-diplomat.json

---

## Purpose

The registry provides:

• transparency for AI agents  
• auditable declaration records  
• a research dataset of agent ecosystems  
• a governance layer for agent identity

---

## License

MIT License
