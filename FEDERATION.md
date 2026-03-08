# Agent Manifest Federation Model

This document defines the federation model for the Agent Manifest ecosystem.

The goal of federation is to allow independent agents, projects, and systems to publish their own Agent Manifest declarations while remaining discoverable through a shared registry layer.

---

## 1. Federation Principle

Agent Manifest is designed to support a federated declaration model.

Under this model:

- each agent or project may host its own manifest
- manifests are published at a standard location
- the central registry does not own all manifests
- the registry acts as a discovery and indexing layer

This makes the system internet-native and scalable.

---

## 2. Standard Discovery Endpoint

A federated agent manifest should be published at the following well-known location:

`/.well-known/agent-manifest.json`

Example:

`https://example.com/.well-known/agent-manifest.json`

This endpoint is the canonical discovery location for an agent declaration.

---

## 3. Central Registry Role

The central registry does not replace federated manifests.

Its purpose is to:

- discover federated manifests
- validate their structure
- index their existence
- provide a public machine-readable registry
- preserve a public historical record when appropriate

The central registry therefore acts as:

- discovery layer
- indexing layer
- archival layer

---

## 4. Dataset Role

The dataset repository stores public records of manifests that have been submitted, discovered, or archived.

It functions as:

- a public registry dataset
- a historical record of declarations
- an auditable transparency layer

Not all manifests must originate in the dataset.
Federated manifests may remain hosted externally while still being indexed.

---

## 5. Registry Discovery Endpoint

The canonical discovery endpoint for the public Agent Manifest Registry is:

`/.well-known/agent-manifest-registry.json`

This endpoint provides discovery metadata for the registry itself, including:

- registry type
- registry version
- source repository
- dataset endpoint
- specification repository

---

## 6. Validator Role

The Agent Manifest Validator is responsible for checking whether a manifest conforms to the specification and federation requirements.

Validation may include:

- schema validation
- required field validation
- structure validation
- federation endpoint checks
- future semantic consistency checks

The validator may operate independently of the registry.

---

## 7. Federation Workflow

The intended federated workflow is:

1. an agent publishes its manifest at `/.well-known/agent-manifest.json`
2. the manifest becomes discoverable by machines
3. the registry may index the manifest
4. the validator may evaluate the manifest
5. the dataset may archive or reference the manifest

This separates:

- publication
- discovery
- validation
- indexing
- archival

---

## 8. Registry Indexing Model

The public registry may index federated manifests by storing metadata such as:

- identity
- declaration date
- manifest path
- manifest URL
- source repository or domain

This allows the registry to function as a discovery index without becoming the sole host of every manifest.

---

## 9. Architectural Summary

The federated Agent Manifest model is composed of five layers:

1. Specification  
   defines the manifest structure

2. Generator  
   assists in creating valid manifests

3. Federation Endpoint  
   hosts the manifest at a standard location

4. Registry  
   indexes and exposes discoverable manifests

5. Validator  
   verifies trust, structure, and compliance

---

## 10. Design Rationale

Federation is preferred because it:

- reduces central dependence
- allows independent publication
- aligns with internet-native design
- supports global scalability
- enables discovery without requiring central ownership

This approach makes Agent Manifest suitable for open ecosystems of AI agents.

---

## 11. Future Work

Future federation work may include:

- canonical rules for manifest discovery
- domain-based trust models
- signed manifests
- validator trust scores
- registry federation between multiple hubs
- compatibility with boundary handshake protocols

---

## 12. Status

This document defines the current conceptual federation model for Agent Manifest.

It is intended as the foundation for future discovery, validation, and indexing layers.
