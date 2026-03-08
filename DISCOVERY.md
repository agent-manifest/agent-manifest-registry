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

Future validator layers may also perform semantic and trust checks.

---

## 6. Registry Output

Once discovered and validated, the registry may index:

- identity
- declaration_date
- manifest_path
- manifest_url
- source domain or repository

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

## 8. Non-Goals

The discovery layer does not guarantee:

- truthfulness of a declaration
- operational safety of an agent
- semantic trustworthiness
- legal identity verification

Those concerns belong to validators, governance processes, or external trust systems.

---

## 9. Discovery Architecture

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
   the system that checks compliance and trust properties

---

## 10. Future Work

Future discovery work may include:

- automatic domain scanning
- repository discovery rules
- signed manifest verification
- trust metadata
- multi-registry federation
- compatibility with validator trust scores

---

## 11. Status

This document defines the conceptual discovery model for the Agent Manifest ecosystem.

It establishes the basis for future crawlers, validators, and federated registry services.
