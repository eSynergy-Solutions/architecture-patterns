# Architecture Patterns

## Purpose

This repository is a collection of architecture patterns designed to address common challenges in infrastructures, platforms, AI, data, and Software Engineering. It provides reusable, well-documented solutions to accelerate design, ensure consistency, and facilitate knowledge sharing. 

By leveraging these patterns, teams can accelerate the delivery of **end-to-end solutions** by using proven architectures that integrate seamlessly across different domains and technologies. This helps reduce development time, minimize risks, and ensure scalability and reliability in production environments.

## Structure

The repository is organized into directories based on domains or categories. Each pattern is documented in a Markdown file and includes diagrams, components, benefits, trade-offs, and cloud-specific implementations.

```
architecture-patterns/
└── Landing-Zones/
    └── AWS/
    └── Azure/
    └── GCP/
└── Patterns/
    └── AI-ML/
        └── RAG.md
        └── ... (other patterns)
└── Use-Cases/
    └── ... (use case examples)
```
### Landing Zones

The `Landing-Zones/` directory provides patterns for cloud landing zone structures. These patterns include best practices for setting up foundational cloud environments for AWS, Azure, and GCP. They cover aspects such as networking, identity, security, and governance.

**Why are Landing Zones important?**

Before we can deploy the architecture patterns and end-to-end solutions, it is essential to have a secure, compliant, and well-structured cloud environment. Landing Zones provide the foundational infrastructure and governance required to ensure that solutions are deployed in a scalable, secure, and compliant manner. They help organizations establish a consistent baseline for cloud environments, enabling faster and safer deployments of applications and services.

### Patterns
- **Problem:** Describes the challenge the pattern addresses.
- **Solution:** Provides a detailed explanation of the architecture and its components.
- **Diagrams:** Visual representations of the architecture.
- **Benefits:** Highlights the advantages of using the pattern.
- **Trade-offs:** Discusses potential drawbacks or limitations.
- **Cloud-Specific Implementations:** Offers guidance on implementing the pattern in AWS, Azure, and GCP.

These patterns are designed to be modular and adaptable, enabling teams to integrate them into their projects with minimal effort.

### Listo f Patterns
List of Patterns can be found here:
* [AI-ML](./Patterns/AI-ML/Index.md)

### Use Cases

The `Use-Cases/` directory demonstrates how the architecture patterns are composed to solve specific business or technical problems. Each use case provides a practical example of how to integrate multiple patterns to achieve a desired outcome.


AI-Powered Red Bar Review
Automated Clause Review:
Users upload contracts into the workflow; the AI agent scans and highlights potential Red Bars.

Accurate Identification:
AI ensures consistent detection of high-risk clauses across all contracts.

Tailored Mitigation Suggestions:
AI proposes mitigation measures based on the specific services, risks, and obligations.

Faster, Safer Approvals:
Streamlined reviews reduce human error, improve compliance, and accelerate project delivery.

### Accelerator Value

<table>
  <thead>
    <tr>
      <th rowspan="2">Component</th>
      <th colspan="4">Deployments</th>
      <th rowspan="2">Status</th>
      <th rowspan="2">Time-save</th>
      <th colspan="3">Accelerators</th>
    </tr>
    <tr>
      <th>GCP</th>
      <th>Azure</th>
      <th>AWS</th>
      <th>K8s</th>
      <th>Used</th>
      <th>Created</th>
      <th>Potential</th>
    </tr>
  </thead>
  <tbody>
    <tr><td colspan="10"><strong>Auto Onboard Bot</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/auto-onboard-backend">auto-onboard-backend</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/auto-onboard-slackbot">auto-onboard-slackbot</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>AB Experiments</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/ab-experiments">ab-experiments</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>PPL PoC</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/ppl-poc">ppl-poc</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Marie Curie Projects</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/marie-curie-london-marathon">marie-curie-london-marathon</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/marie-curie-classifier">marie-curie-classifier</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>RAG Proofs of Concept</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/rag-backend">rag-backend</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/rag-poc-backend">rag-poc-backend</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/rag-chat-any-website">rag-chat-any-website</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/ollama-rag">ollama-rag</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Red Bar Tool</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/red-bar-tool-frontend">red-bar-tool-frontend</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/red-bar-tool-backend">red-bar-tool-backend</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Generative BI Assistant</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/generative-bi">generative-bi</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Back-Office Tool</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/back-office-tool-backend">back-office-tool-backend</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/back-office-tool-frontend">back-office-tool-frontend</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/back-office-tool-add-in">back-office-tool-add-in</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Back-Office Doc Intelligence</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/back-office-doc-intelligence">back-office-doc-intelligence</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Collibra Adaptor</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/collibra-adaptor">collibra-adaptor</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/collibra-adaptor-sandbox-dc-tenant">collibra-adaptor-sandbox-dc-tenant</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/collibra-adaptor-sandbox-tenant">collibra-adaptor-sandbox-tenant</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Sales AI Assistant</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/sales-ai-assistant">sales-ai-assistant</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>GenAI Playbook</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/GenAI_Playbook">GenAI_Playbook</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Snowflake Cortex</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/snowflake-cortex">snowflake-cortex</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>eSynergy Open RAG</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/esynergy-open-rag">esynergy-open-rag</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Converse</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/Converse">Converse</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>D3 World Map LinkedIn Contacts</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/d3-world-map-linkedin-contacts">d3-world-map-linkedin-contacts</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>LinkedIn Scraper API</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/linkedin-scraper-api">linkedin-scraper-api</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Dual AI Policy Data Extractor PoC</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/dual-ai-policy-data-extractor-poc">dual-ai-policy-data-extractor-poc</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
    <tr><td colspan="10"><strong>Marine Insurance</strong></td></tr>
    <tr>
      <td>└── <a href="https://github.com/eSynergy-Solutions/marine_insurance">marine_insurance</a></td>
      <td></td><td></td><td></td><td></td>
      <td>✅</td><td></td>
      <td></td><td></td><td></td>
    </tr>
  </tbody>
</table>
