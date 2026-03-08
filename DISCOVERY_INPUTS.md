# Agent Manifest Discovery Inputs

This document defines the possible input sources that allow the Agent Manifest Registry to discover candidate agent declarations.

Discovery inputs represent the starting point for the registry discovery process.

They provide domains, repositories, or direct manifest references that the registry may evaluate for indexing.

---

# 1. Purpose

The purpose of discovery inputs is to provide flexible entry points for identifying agents that may have published an Agent Manifest.

The registry does not require all manifests to be submitted manually.

Instead, multiple discovery inputs may lead to the same result:

• locating a valid agent manifest  
• validating its structure  
• indexing the declaration in the public registry  

---

# 2. Direct Manifest Submission

The most explicit discovery input is a direct manifest submission.

Example:

```
https://example.com/.well-known/agent-manifest.json
```

In this case the registry directly evaluates the provided manifest URL.

This method is typically used for manual submissions through repository issues.

---

# 3. Agent URL

An agent may be introduced to the registry using a base URL.

Example:

```
https://example.com
```

The registry then attempts to discover the manifest automatically by checking:

```
https://example.com/.well-known/agent-manifest.json
```

If the endpoint exists and contains a valid manifest, the agent becomes discoverable.

---

# 4. Repository URL

Agent declarations may also be associated with public repositories.

Example:

```
https://github.com/example/project
```

The registry may attempt to detect a manifest in common locations such as:

```
/.well-known/agent-manifest.json
agent-manifest.json
manifest.json
```

Future discovery tools may use repository metadata or repository scanning to locate candidate manifests.

---

# 5. Curated Discovery Lists

Curated lists may also act as discovery inputs.

Examples include:

• research datasets  
• curated agent directories  
• experimental registries  
• ecosystem partner lists  

These lists may contain candidate agent URLs that the registry can evaluate.

---

# 6. Automated Crawlers

Future versions of the registry may support automated discovery.

Examples:

• scanning public repositories  
• domain crawling  
• registry federation between multiple hubs  

Automated crawlers may attempt to locate well-known endpoints that expose agent manifests.

---

# 7. Validation Before Indexing

Regardless of the discovery input source, the registry should validate the discovered manifest before indexing.

Validation may include:

• JSON validity  
• schema compliance  
• presence of required fields  
• structural integrity  

Only validated manifests should appear in the public registry.

---

# 8. Multiple Input Paths

The same manifest may be discovered through different inputs.

Example:

```
manual issue submission
↓
agent URL submission
↓
automated crawler
```

The registry should treat these as equivalent discovery events referring to the same manifest.

---

# 9. Registry Output

Once validated, the registry may store the following metadata:

• identity  
• declaration date  
• manifest URL  
• source domain or repository  
• discovery method  

This allows transparency regarding how a manifest was discovered.

---

# 10. Design Philosophy

Discovery inputs are intentionally flexible.

The Agent Manifest ecosystem supports:

• manual discovery  
• semi-automated discovery  
• fully automated discovery  

This allows the system to evolve gradually without requiring complex infrastructure at the beginning.

---

# 11. Status

This document defines the initial model for discovery inputs in the Agent Manifest ecosystem.

Future revisions may expand discovery mechanisms as the ecosystem grows.
