# Microsoft Foundry and Agent 365

## Define runtime policies with Agent Controls

**Availability:** Public preview.

Agent Controls gives you a managed service for storing and evaluating policies that govern what agents do, not just what they say. Built on the open-source [Agent Control Specification (ACS)](https://github.com/responsibleai/agent-control-spec), it lets you manage policies centrally and bind them to Azure resources rather than duplicate policy logic in every application. At runtime, an agent sends the proposed action or content for evaluation and receives an allow, deny, or transform verdict, along with a receipt identifying the policy version used.

The samples show how to test rules locally, then publish policies and evaluate agent runtime behaviors. Examples include refund limits, approved tools and document destinations, Content Safety checks, and LLM-based reviews. Foundry agents have built-in enforcement for policy evaluation outputed verdicts; agents hosted elsewhere can enforce the returned verdict themselves, with [Agent Hooks](https://github.com/responsibleai/agent-hooks) providing a standard integration contract.

**Link to doc:** [Agent Controls (public preview)](https://aka.ms/FoundryAgentControls)

**Code samples:** [Agent Controls samples](https://github.com/microsoft-foundry/foundry-samples/tree/main/samples/cli/agent-controls)

## Add custom rules to Foundry guardrails

**Availability:** Private preview.

Built-in safety checks address common risks, but your application might also need rules specific to your business. Custom policies in Foundry guardrails add deterministic checks for patterns, keywords, and allow or block lists, alongside LLM judges for requirements that need contextual interpretation. For example, an HR assistant could use a judge to check whether a response stays on topic, while a deterministic rule checks for a prohibited term.

These policies work alongside Azure AI Content Safety classifiers supported by existing Foundry Guardrail experience, so business rules and standard safety controls can be configured together. The guardrails overview explains how controls apply to user input, tool calls, tool responses, and final output, and how guardrails are assigned to models and agents. LLM judges for custom policies require a model deployed in the same project that supports chat completions.

**Link to blog:** [Custom policies in Foundry guardrails](https://aka.ms/FoundryCustomGuardrails)

**Request private preview access:** [Custom guardrail policies signup](https://aka.ms/FoundryCustomGuardrailsPreview)

**Link to doc:** [Guardrails and controls overview in Microsoft Foundry](https://aka.ms/FoundryCustomGuardrailsDocs)

## Author and manage policies in Foundry Compliance

**Availability:** Public preview for policy authoring and management; private preview for ACS runtime policy support in Foundry Compliance.

Foundry Compliance lets you author and manage policies for approved models and publishers, agent types and hosted-agent images, tool usage and connections, network egress, and required safety controls. These policies use Azure Policy to establish requirements across a subscription or resource group. In **Manage** > **Compliance**, review compliance by policy or asset, inspect violations, and navigate to the appropriate management experience for remediation. Audit reports noncompliance; Deny, where supported, blocks noncompliant create or update operations rather than stopping existing agent runs.

ACS runtime policies add behavioral rules checked while agents run, alongside the broader policy types above. This Foundry Compliance integration is in private preview; the other policy types don't require ACS private preview access. For ACS runtime rules, subscription- or resource-group-level policies coexist with resource-level guardrails, with the stricter verdict taking precedence when both apply. The compliance experience also surfaces Microsoft Defender for Cloud security recommendations and Microsoft Purview data-governance signals, with specialized investigation and remediation handled in those services.

**Link to blog:** [Governance and compliance in Microsoft Foundry](https://aka.ms/FoundryPolicyCompliance)

**Request ACS policy private preview access:** [ACS runtime policies in Foundry Compliance signup](https://aka.ms/FoundryPolicyCompliancePreview)

**Link to doc:** [Manage compliance and security in Microsoft Foundry](https://aka.ms/FoundryPolicyComplianceDocs)

## Govern Foundry agents across your tenant with Agent 365

**Availability:** Preannouncement.

Agent 365 policies experience will give your IT team a central place to set runtime policies for Foundry agents across your tenant. Agent 365 will automatically create matching Azure Policy assignments to enforce those rules across subscriptions.

IT administrators who already manage Microsoft 365 will be able to govern Foundry agent behavior without configuring Azure Policy directly. A shared, tenant-wide policy baseline reduces repeated setup and helps keep agent deployments aligned with organizational requirements as adoption grows.

**Link to blog:** [Tenant-wide Foundry policies in Agent 365](https://aka.ms/FoundryAgent365Policies)
