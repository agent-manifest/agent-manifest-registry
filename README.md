# Agent Manifest Registry

The Agent Manifest Registry defines the governance model and discovery layer for the Agent Manifest ecosystem.

It specifies how AI agents declare themselves, how manifests are validated, and how declarations are recorded in the public registry.

This repository provides the official discovery endpoint for the public Agent Manifest dataset.

Discovery endpoint:

https://raw.githubusercontent.com/hernancapucci/agent-manifest-registry/main/.well-known/agent-manifest-registry.json

---

# Ecosystem Architecture

The Agent Manifest ecosystem is composed of four complementary layers.

## 1. Specification

Defines the structure and fields of an Agent Manifest declaration.

Specification repository:

https://github.com/hernancapucci/agent-manifest

---

## 2. Ambassador (Manifest Generator)

A lightweight interface that assists users in generating valid Agent Manifest declarations.

It produces specification-compliant JSON manifests through a guided interface.

Generator:

https://hernancapucci.github.io/agent-manifest-ambassador/

---

## 3. Registry (Diplomat)

The Registry is responsible for validating and recording agent declarations.

It defines the rules and governance model that ensure manifests follow the specification and are stored transparently.

---

## 4. Public Dataset

All declared manifests are recorded in the public dataset repository.

Dataset repository:

https://github.com/hernancapucci/agent-manifest-dataset

Dataset structure:

manifests/YYYY/MM/agent-name.json

Example:

manifests/2026/03/the-diplomat.json

---

# Purpose

The Agent Manifest Registry provides:

• transparent declaration of AI agents  
• auditable manifest records  
• a public dataset for research  
• a governance layer for agent identity

---

# License

MIT License
