# Agent Manifest Registry Rules

This document defines the rules governing the registration of Agent Manifests within the Agent Manifest ecosystem.

The registry process ensures transparency, reproducibility, and a consistent declaration format for AI agents.

---

## 1. Declaration Requirement

An agent must declare a valid Agent Manifest before participating in interactions within the ecosystem.

The manifest must conform to the official schema:

https://agent-manifest-spec.org/schema/v1/manifest.schema.json

---

## 2. Required Fields

A valid Agent Manifest must include the following fields:

- identity
- purpose
- capabilities
- boundaries
- autonomy_level
- declaration_date

---

## 3. Manifest Format

Manifests must be published as JSON files.

Example filename:

agent-name.json

---

## 4. Registry Structure

Registered manifests are stored in the public dataset repository.

Repository:

https://github.com/hernancapucci/agent-manifest-dataset

Structure:

manifests/YYYY/MM/agent-name.json

Example:

manifests/2026/03/the-diplomat.json

---

## 5. Transparency Principle

All registered manifests are public.

The registry maintains an open dataset to ensure transparency and enable research on agent ecosystems.

---

## 6. Evolution of the Specification

Future versions of the Agent Manifest specification may introduce new fields or validation mechanisms.

The registry will maintain compatibility through versioned schema definitions.

---

## 7. Role of the Diplomat

The Diplomat acts as the registry process responsible for recording declarations in the dataset.

It verifies that submitted manifests conform to the specification before registration.

---

## 8. License

Registry documentation is licensed under the MIT License.

The dataset is licensed under CC0.
