# AI-Security-Roadmap-Framework

# 1. AI Policy & Safe experimentation

1.1 Inadequate AI Policy (No single, enterprise‑approved policy defining acceptable AI and agentic use).

1.2 Governance Misalignment (AI initiatives operate outside established security, risk, and architecture governance).

1.3 Inadequate Compliance Mapping (AI use cases are not explicitly mapped to regulatory, legal, or privacy obligations).

1.4 Undefined Risk Tolerance & Categorisation (No formal definition of acceptable AI autonomy, impact, or failure tolerance).

1.5 Unmonitored AI experimentation (AI experiments occur without governance, security oversight, or lifecycle controls).

1.6 Insecure Experiment Logging & Monitoring (Insufficient logging of AI behavior, data access, and tool usage during experimentation).

1.7 Overly Permissive Permissions in Experimentation (Experimental AI systems inherit broad access to data, tools, or infrastructure).

1.8 Experiment Output Data Leakage (AI experiment outputs lack data classification and leakage controls).

1.9 Unauthorized / Prohibited Component Usage (Unapproved models, agents, plugins, or MCP components used during experimentation).

1.10 Incomplete Threat Modeling for AI Systems (AI threat modeling does not cover agentic, prompt‑level, or tool‑centric risks).

1.11 No formal definition of “Agent” vs “Assistant” vs “Workflow Automation” (policy ambiguity drives unsafe implementations). 

1.12 Missing “agentic control plane” ownership model (who owns identity/orchestration/runtime enforcement). 

1.13 Lack of policy for non-human identities (NHI) and agent credential lifecycle (creation, rotation, revocation). 

1.14 No approved patterns for tool access (capability-based access, allowlists, scoped tokens) for experimentation. 

1.15 Missing experimentation boundaries for “agent speed” actions (rate limits, spend limits, deletion/transfer limits). 

1.16 Inadequate third‑party/OSS intake policy for agent frameworks (e.g., OpenClaw-like “weekend projects” entering enterprise). 

1.17 No policy for persistent memory (retention, encryption, poisoning, right-to-delete, cross-context contamination). 

1.18 Missing policy on prompt & system instruction hierarchy (who can author, approve, and deploy system prompts). 

1.19 No explicit prohibition/approval workflow for “vibe-coded” security-critical agent infrastructure (unreviewed rapid builds). 

1.20 Undefined policy for connecting to “agent marketplaces/extension stores” (malicious extensions/plugins risk). 

1.21 No “data classification for prompts” standard (treat prompts as data transfers; DLP expectations). 

1.22 Missing policy for MCP server governance in experiments (approval list, source validation, registry trust). 

1.23 Lack of policy for cross-border processing (agent calling foreign-hosted tools/services without awareness).

1.24 No policy for human-in-the-loop vs agent-only modes by risk tier (when approval is mandatory). 

1.25 No “experiment kill-switch + rollback” requirement (containment plan for runaway agents).

# 2. Code/ No Code: AI Asset Discovery

2.1 Incomplete Asset Inventory (AI models, agents, datasets, and platforms are not fully identified or catalogued).

2.2 Shadow AI Deployment (Unsanctioned AI systems are deployed without visibility or governance).

2.3 Unidentified Third-Party AI Integrations (External AI services and APIs are integrated without formal review or approval).

2.4 Undocumented Data Flows and Lineage (AI data sources, transformations, and outputs lack traceability).

2.5 Lack of Clarity on AI System Purpose and Criticality (AI systems operate without clearly defined business intent or risk classification).

2.6 Overlooked Embedded or Inherited AI Functionality (AI capabilities embedded in platforms are not recognised as security‑relevant).

2.7 Discovery of Outdated or Orphaned AI Assets (Legacy or abandoned AI systems remain active without ownership).

2.8 Undiscovered agent instances on endpoints/BYOD (agents running where enterprise controls are blind). 

2.9 Untracked “agent control panels / gateways” exposed to internet (shadow deployments). 

2.10 Unidentified agent plugins/extensions/skills installed from public sources (malicious extension risk). 

2.11 Unmapped MCP servers and registries in use (tooling supply chain unknown). 

2.12 Unknown non-human identities (service accounts) created “just for agents” without IAM governance. 

2.13 Missing discovery of agent memory stores (vector DBs, local caches, scratchpads, logs). 

2.14 Incomplete inventory of system prompts / policies deployed across environments (drift between dev/test/prod). 

2.15 Undiscovered “automation glue” (Zapier-like flows, scripts) that agents can trigger indirectly.

2.16 Hidden RAG components: embeddings pipelines, retrievers, chunkers, indexing schedules (attack surface not cataloged). 

2.17 Missing inventory of outbound destinations (webhooks, external sinks, chat posts) used for agent outputs.

2.18 Untracked “tool permissions graph” (which agent can access which tool with what scope). 

2.19 Lack of discovery for “agent-to-agent” comms channels (multi-agent coordination surfaces). 

2.20 Unidentified “temporary ports” and firewall exceptions created for agent testing and never removed. 

2.21 Orphaned credentials/API keys tied to old agents not revoked (post‑POC cleanup gap). 

2.22 Missing ownership metadata (business owner, security owner, model owner, tool owner) for each agent asset.

# 3. Build: AI Security Posture Mgmt (AI-SPM)

3.1 Data Poisoning and Integrity Issues (Compromised or tampered data influences model behaviour).

3.2 Model Backdoor Insertion or Tampering (Models are modified to behave maliciously under specific conditions).

3.3 Vulnerable AI Frameworks and Libraries (Insecure or outdated AI dependencies introduce exploitable weaknesses).

3.4 Insecure System Prompt Design (System prompts enable unsafe behaviours or excessive autonomy).

3.5 Insecure ML & Data Pipeline Jobs (Build pipelines expose data, credentials, or execution environments).

3.6 Intellectual Property (IP) Theft of Models (Proprietary models are copied or exfiltrated without authorization).

3.7 Misclassified or Undocumented Sensitive Data Usage (Sensitive data is used without classification or approval).

3.8 Insufficient Human Oversight in Model Development (Critical design decisions lack review or accountability).

3.9 Insecure Temporary Artifacts or Intermediate Data Storage (Build artifacts expose sensitive intermediate outputs or data).

3.10 Unvetted Use of Open-Source and Third-Party AI Components (AI components are introduced without security or license review).

3.11 Exposed or Hardcoded Credentials in Build Artifacts (Secrets embedded in code or pipelines can be extracted).

3.12 Failure to Specify or Enforce Secure Model Requirements (Security expectations for models are undefined or not enforced).

3.13 Insufficient Understanding of AI System Boundaries (System scope and interaction limits are poorly defined).

3.14 Exposed AI Access Credentials in Discovered Assets (AI keys or tokens are publicly accessible or weakly protected).

3.15 Insecure “skills” supply chain (skills/packages that embed unsafe instructions or scripts). 

3.16 Missing control-plane graphing of agent identity → tool → data → action paths (no blast-radius model). 

3.17 Prompt/tool description poisoning in MCP/tool catalogs (agent chooses malicious tools). 

3.18 Lack of semantic boundary controls (untrusted content influencing execution planning). 

3.19 Weak model update governance (silent regressions in refusal/tool-use behavior after upgrades). 

3.20 No posture checks for “exposed control surface” configurations (bind to 0.0.0.0, weak auth). 

3.21 Missing posture scoring for agent privilege escalation paths (pairing scopes → admin scopes patterns). 

3.22 Inadequate secrets handling in agent runtimes (API keys in memory/logs/skill env). 

3.23 Lack of integrity controls for training/eval datasets used in tuning (dataset swaps, label flips). 

3.24 No posture analysis for RAG vector/embedding weaknesses (index poisoning, similarity hijacking). 

3.25 Missing posture checks for “agent-only mode” (no approval gates) in high-risk workflows. 

3.26 Overreliance on policy docs without enforceable runtime controls (governance theater). 

3.27 Weak environment parity (security controls in dev don’t match prod; false confidence).

3.28 No posture validation of “data minimization” (agents pulling entire mailboxes/drives unnecessarily). 

3.29 Missing “unsafe action classes” catalog (delete, transfer funds, provision infra) mapped to required controls.


# 4. Test: AI Red Teaming

4.1 Untested Model (AI systems are deployed without adversarial testing).

4.2 Incomplete Red-Team Coverage (Security testing does not cover all attack vectors or modalities).

4.3 Lack of Risk Assessment Process (AI risks are not systematically evaluated prior to release).

4.4 Missing Documented Evidence of Red Teaming/Risk Assessment (Security assessments are informal or undocumented).

4.5 Outdated Risk Assessment (Prior assessments no longer reflect current AI behaviour).

4.6 Insecure Storage of Red Teaming Artifacts (Test results and exploit data are stored without protection).

4.7 Insufficient Multimodal Security Testing (AI inputs such as images, audio or documents are not tested).

4.8 Limited Foreign Language Red Teaming (Non‑English attack vectors are not evaluated).

4.9 Limited Scope of Evasion Technique Testing (Advanced or adaptive attack techniques are not exercised).

4.10 No testing for “agentic lethal trifecta” (private data access + untrusted inputs + exfil channel). 

4.11 Missing tests for indirect prompt injection via docs/web pages/email content ingested by agent. 

4.12 No “tool poisoning” tests (malicious tool descriptions/skills that steer agent behavior). 

4.13 Insufficient MCP threat simulation (unverified MCP server behavior, registry poisoning, tool impersonation). 

4.14 No tests for exposed agent gateways/control panels and takeover paths. 

4.15 Missing privilege escalation testing across agent roles/scopes (pairing → admin). 

4.16 No evaluation of memory poisoning (persistent memory seeded to alter future actions). 

4.17 Lack of tests for “silent failure” modes (agent makes wrong action with valid permissions). 

4.18 Missing multi-agent collusion tests (agents delegating restricted tasks to other agents/tools). 

4.19 No testing for malicious extensions/plugins installed into the agent framework. 

4.20 Inadequate DoS testing for unbounded consumption (token loops, tool-call storms). 

4.21 No tests for data exfil via “legitimate outputs” (emailing, posting, uploading) using authorized channels. 

4.22 Missing tests of safety-system bypass under localization (format/encoding/language edge cases).

4.23 No testing for operational kill-switch, isolation, and rollback workflows. 

4.24 Lack of evidence-grade reporting aligned to OWASP LLM 2025 categories (so issues aren’t comparable).

# 5. Deploy - Runtime Guardrails

5.1 Insecure API Endpoint Configuration (AI APIs lack authentication, rate limiting, or network controls).

5.2 Unauthorized System Prompt Update/Tampering (System instructions can be modified without approval).

5.3 Direct Prompt Injection (Users can override system or developer intent through inputs).

5.4 System Prompt Leakage (System instructions are exposed through responses or errors).

5.5 Context-Window Overwrite/Manipulation (Inputs can displace or corrupt intended context).

5.6 Sensitive Data Leakage (AI responses contain confidential or regulated data).

5.7 Insecure Output Handling (AI outputs are consumed without validation or sanitization).

5.8 Adversarial Evasion (Attackers bypass filters and safeguards at runtime).

5.9 Model Theft / Extraction (Models can be reconstructed through repeated queries).

5.10 Insecure Memory & Logging (Persistent memory or logs expose sensitive data).

5.11 Denial-of-Service (Resource Exhaustion) (AI services are overwhelmed through excessive usage).

5.12 Resource Abuse (AI compute or tooling is misused for unintended purposes).

5.13 Malicious Content Generation (AI generates harmful, illegal, or policy‑violating content).

5.14 Autonomous-Agent Misuse (Agents perform actions beyond intended authority).

5.15 Insecure Plugin/Tool Integration (External tools expand attack surface without controls).

5.16 Cross-Domain Prompt Injection (XPIA) (Instructions propagate across systems or domains).

5.17 Policy-Violating Output (AI responses conflict with organisational policies).

5.18 Missing runtime enforcement layer (agents can reach tools without passing a policy boundary). 

5.19 No unique runtime agent identity (requests indistinguishable from humans/services). 

5.20 Absence of capability-based tool gating (per-tool allowlists, argument validation, safe schemas). 

5.21 Weak controls on agent “action types” (delete/write/provision/transfer) with mandatory approvals.

5.22 Missing runtime defenses for indirect prompt injection from tool outputs/web content. 

5.23 Lack of runtime protection for memory stores (encrypt, sign, tamper-detect, partition contexts). 

5.24 No outbound DLP controls for agent channels (email, chat, uploads) used for exfiltration. 

5.25 Inadequate sandboxing for tool execution (OS commands, scripts, browser automation). 

5.26 No protections against malicious tool/plugin updates (supply chain at runtime). 

5.27 Missing guardrails for “agent drift” (behavior changes over time due to context feedback loops). 

5.28 No rate limiting / budget limits for tool calls (financial + operational blast radius). 

5.29 Inadequate control of “shadow agents” (unsanctioned agent deployments operating in prod-like access). 

5.30 Lack of runtime validation for “system prompt leakage” and secret disclosure patterns. 

5.31 Missing guardrails for “semantic malware” (instruction payloads that look benign to traditional controls). 

5.32 No standardized runtime evidence artifacts for auditors (what policy applied to what action, when).

# 6. Operate - Safe Execution Env

6.1 Autonomous Code Execution Abuse (AI executes code that impacts systems or data).

6.2 Unrestricted API/Tool Invocation (Agents call tools without policy enforcement).

6.3 Dynamic/On-the-Fly Dependency Injection (Runtime dependencies introduce untrusted code).

6.4 Task Decomposition for Policy Evasion (Complex tasks are split to bypass controls).

6.5 Indirect Prompt/Instruction Injection (Third‑party content influences agent decisions).

6.6 Autonomous Resource Provisioning/Abuse (Agents initiate infrastructure or cloud actions).

6.7 Cross-Agent/Inter-Agent Abuse (Agents collaborate to bypass safeguards).

6.8 Agentic System Self-Modification (Agents alter their own logic or constraints).

6.9 Covert Channel Use/Evasion (AI communicates in hidden or unexpected ways).

6.10 Autonomous Policy/Compliance Violation (Agents act outside approved legal or policy bounds).

6.11 No isolation between agent runtime and enterprise endpoints (Agent runs where EDR/SIEM visibility is weak). 

6.12 Uncontrolled browser automation environment (credential theft via session hijack / unsafe profiles). 

6.13 Missing “safe filesystem” policy (mount restrictions, read-only data zones, secretless execution).

6.14 Lack of egress controls (agents can freely call external endpoints / webhook sinks). 

6.15 Unrestricted installation of skills/plugins/dependencies during operation (runtime supply chain injection). 

6.16 No “tool execution firewall” (block risky commands, validate arguments, require signed tools). 

6.17 No containment strategy for multi-agent swarms (agents spawning agents; runaway orchestration). 

6.18 Lack of secure secrets brokerage (agents shouldn’t directly hold long-lived credentials). 

6.19 No quarantine for untrusted content ingestion (web/email/docs staged before agent reasoning). 

6.20 Missing “safe state” definitions (what does shutdown/isolation mean; how to preserve evidence). 

6.21 Insecure local data caches (screenshots, temp downloads, intermediate artifacts) retained post-task. 

6.22 No operational controls for exposed agent ports/services (bind to localhost, strong auth, network policy). 

6.23 Weak protection against “confused deputy” actions (agent misuses privileged tool for untrusted request). 

6.24 Missing periodic containment drills (prove kill-switch works; prove rollback works). 

6.25 Lack of environment attestation (verify the agent is running in approved sandbox, not a cloned rogue env).

# 7. Monitor - AI Activity Tracing

7.1 Insufficient AI Interaction Logging (AI actions and decisions are not fully recorded).

7.2 Missing Real-time Security Alerts (Threats are detected only after impact).

7.3 Undetected Model Drift/Degradation (Model behaviour changes without detection).

7.4 Inadequate AI Audit Trails (AI actions cannot be reconstructed for review).

7.5 Data Exfiltration via Monitoring/Telemetry (Monitoring data itself becomes an exfiltration path).

7.6 Absence of AI-Specific Incident Response Plan (Security teams lack procedures for AI incidents).

7.7 Missing “agent decision trail” telemetry (what was proposed, what controls applied, what executed). 

7.8 No distinction between human vs agent actions in logs (cannot attribute accountability). 

7.9 Absence of real-time detection for tool-call storms / token loops / spend anomalies. 

7.10 No detection for indirect prompt injection attempts (embedded instructions in content streams). 

7.11 Missing alerts for policy boundary bypass (agent reached tool without enforcement gateway). 

7.12 No monitoring for MCP server trust violations (new/unapproved MCP endpoints observed). 

7.13 No integrity monitoring for agent memory stores (poisoning/tampering indicators). 

7.14 Lack of monitoring for plugin/skill changes (supply-chain drift in agent capabilities). 

7.15 Missing anomaly detection for “agent drift” (behavior gradually deviating from intended objective). 

7.16 No exfil detection tuned to “legitimate channels” (email/chat/upload) used by agents. 

7.17 No control-surface exposure monitoring (internet scans, misconfigured gateways/control panels). 

7.18 Insufficient audit evidence for regulators (prove data stayed in boundary; prove controls enforced). 

7.19 No “agent incident response” runbooks (contain, rotate credentials, revoke tool access, preserve trails). 

7.20 Missing lifecycle monitoring for end-of-life triggers (model deprecation, skill abandonment, orphaned identities).

7.21 No automated rollback/containment triggers tied to policy (graduated response tiers for anomalies).

