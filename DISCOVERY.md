# Agent Manifest Discovery Model

This document defines how the Agent Manifest Registry discovers and indexes federated agent declarations.

The purpose of discovery is to make independently hosted Agent Manifests visible to registries, validators, and other agents through a predictable web location.

---

## 1. Discovery Principle

Agent Manifest discovery is federated.

This means that the registry does not need to host every manifest directly.

Instead, agents and projects may publish their own manifest at a standard location, and the registry may discover and index those declarations.

---

## 2. Canonical Agent Discovery Endpoint

The canonical discovery endpoint for an individual agent declaration is:

/.well-known/agent-manifest.json

Example:

https://example.com/.well-known/agent-manifest.json

If this endpoint is present, the agent is considered discoverable within the Agent Manifest ecosystem.

---

## 3. Registry Discovery Process

The registry discovery process is conceptually defined as follows:

1. identify a candidate domain, repository, or service
2. request the well-known endpoint
3. check whether a valid Agent Manifest is present
4. validate the manifest structure
5. index the manifest in the public registry
6. optionally archive the manifest in the public dataset

This separates publication from indexing.

---

## 4. Sources of Discovery

The registry may discover manifests from multiple sources, including:

- direct submission by repository issue
- manually submitted agent URLs
- curated discovery lists
- public repositories that expose the well-known endpoint
- future automated crawlers

The discovery model allows both manual and automatic indexing.

---

## 5. Validation Before Indexing

Discovery alone is not sufficient for indexing.

Before a manifest is added to the registry, the system should verify:

- the endpoint exists
- the file is valid JSON
- required Agent Manifest fields are present
- the declaration is structurally valid

Semantic checks are a possible future research direction (non-normative).

---

## 6. Registry Output

Once discovered and validated, the registry may index:

- `agent_id`
- `registered_at`
- `manifest_path`
- `manifest_url`
- source domain or repository

Registry output fields are index metadata maintained by the registry, distinct from the manifest fields defined by the Agent Manifest specification.

This allows machine-readable discovery without requiring central ownership of every manifest.

---

## 7. Relationship to the Dataset

The dataset acts as a public registry and historical archive.

A discovered manifest may be:

- referenced only
- indexed in the registry
- archived in the dataset
- revalidated in the future

This allows the registry to remain lightweight while preserving transparency.

---

## 8. Registry Discovery Document

The registry publishes a discovery document at:

`/.well-known/agent-manifest-registry.json`

on the canonical host, `agent-manifest-spec.org`. It points at the public
registry index and at the repositories behind it.

### Field names and their stability

The canonical key for the location of the registry index is `registry_url`.

The document declares its own `registry_version`. **The names of its fields are
stable for as long as that number is unchanged.** Renaming, removing, or
repurposing a field requires incrementing it. A tool may therefore read this
document by field name, provided it reads `registry_version` as well and treats
an unrecognised value as a document it does not know how to parse.

### What this contract is not

This is an operational contract of the registry. **It is not part of the
normative specification.** The normative contract is defined by
`spec/v1.0/spec.md` and `spec/v1.0/schema.json`, as stated in `STABILITY.md`, and
nothing in this section extends it. A change to the fields described here is not
a change to the Agent Manifest specification and does not affect
`manifest_version`.

### Two different version numbers

`registry_version` appears in two distinct documents, and they are independent:

| Where | What it versions |
| --- | --- |
| `/.well-known/agent-manifest-registry.json` | the field names of the discovery document described in this section |
| `registry.json`, in the public dataset | the structure of the registry index itself |

They are separate contracts that happen to share a field name. Neither number
governs the other, and neither governs `manifest_version`.

### The copy in this repository

This repository carries a copy of the discovery document for reference. **The
document served on the canonical host is the one that counts.** Where the two
differ, the served document is correct and the copy here is stale.

---

## 9. Non-Goals

The discovery layer does not guarantee:

- truthfulness of a declaration
- operational safety of an agent
- semantic trustworthiness
- legal identity verification

Those concerns belong to validators, governance processes, or external trust systems.

---

## 10. Discovery Architecture

The discovery architecture of Agent Manifest consists of:

1. publisher  
   an agent or project hosting its own manifest

2. discovery endpoint  
   the standard well-known manifest location

3. registry  
   the system that indexes discovered manifests

4. dataset  
   the public archive of indexed declarations

5. validator  
   the system that checks structural conformance of declarations

---

## 11. Future Work

Future discovery work may include (possible future research, non-normative):

- automatic domain scanning
- repository discovery rules
- signed manifest verification
- multi-registry federation

---

## 12. Status

This document defines the conceptual discovery model for the Agent Manifest ecosystem.

It establishes the basis for future crawlers, validators, and federated registry services.
