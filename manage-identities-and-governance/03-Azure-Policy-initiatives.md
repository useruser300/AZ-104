# Azure Policy Initiatives

## 1. Azure Policy Initiatives

Azure Policy initiatives are used to enforce organizational standards, assess compliance at scale, and manage Azure resources effectively.

An Azure Policy initiative is a collection of Azure Policy definitions grouped together for a specific goal or purpose.

Instead of assigning many individual policies one by one, you can group them into one initiative and assign that initiative as a single item.

Main idea:

```text
Policy Definition = one governance rule
Policy Initiative = a group of related governance rules
```

Azure Policy initiatives help organizations:

- Enforce organizational standards.
- Assess compliance at scale.
- Manage Azure resources consistently.
- Apply centralized governance.
- Track compliance for larger goals.
- Support regulatory and industry compliance requirements.

Examples of initiative goals:

- Enforce tagging standards.
- Enforce allowed Azure regions.
- Enforce security baseline requirements.
- Enforce data residency rules.
- Track compliance with regulatory frameworks.
- Apply sovereignty-focused compliance controls.

This module focuses on:

- Cloud governance with Azure Policy.
- Azure Policy and its components.
- Azure Policy initiatives.
- Policy definitions.
- Policy assignments.
- Policy evaluation.
- Policy effects.
- Safe deployment practices.
- Event-based reactions to policy state changes.

---

## 2. What Is Azure Policy?

Azure Policy is a governance service in Azure.

It allows you to create, assign, and manage policies that enforce rules over Azure resources.

Azure Policy helps ensure that Azure resources stay compliant with:

- IT governance standards.
- Organizational standards.
- Regulatory standards.
- Service-level agreements.

Azure Policy definitions are written in JSON.

Azure Policy can:

- Audit resources.
- Block noncompliant resource creation.
- Modify resources.
- Deploy missing configurations.
- Track compliance.
- Help remediate noncompliant resources.

Simple idea:

```text
Azure Policy checks Azure resources against business rules.
If a resource does not follow the rule, Azure Policy can audit it, deny it, modify it, or remediate it.
```

---

## 3. Azure Policy and Cloud Governance

Cloud governance means managing how cloud resources are used inside an organization.

Azure Policy is one of the most important tools for cloud governance in Azure.

It helps organizations:

- Control resource usage.
- Prevent misconfigurations.
- Enforce security standards.
- Enforce compliance requirements.
- Track resource compliance.
- Apply guardrails across teams and environments.

Azure Policy is important because cloud environments can grow quickly. Without governance, teams may create resources that are insecure, expensive, inconsistent, or noncompliant.

---

## 4. Microsoft Cloud Adoption Framework for Azure

Microsoft Cloud Adoption Framework for Azure is a full guidance framework that helps organizations plan, implement, govern, and operate Azure environments.

It helps:

- Cloud architects.
- IT teams.
- Business leaders.

The framework includes:

- Best practices.
- Documentation.
- Tools.
- Methodologies.
- Technical and business guidance.

Azure Policy plays an important role in the Govern methodology of the Cloud Adoption Framework.

---

## 5. Purpose of the Cloud Adoption Framework

CAF helps organizations answer important questions such as:

- Why are we moving to Azure?
- What business outcomes do we want?
- How should we prepare Azure?
- How do we migrate workloads?
- How do we govern resources?
- How do we operate and optimize the environment?

Simple idea:

```text
CAF is not only about using Azure services.
It is about planning, organizing, governing, and operating cloud adoption correctly.
```

---

## 6. High-Level Structure of CAF

The Cloud Adoption Framework can be understood through three main perspectives:

| Perspective | Focus |
|---|---|
| Business | Strategy and planning |
| Platform | Azure environment preparation and governance |
| Workload | Migration, innovation, and operations |

---

## 7. Business Perspective

The Business perspective focuses on defining why the organization wants to adopt Azure and how the adoption should be planned.

### Define Strategy

This step focuses on understanding the business reason for moving to Azure.

Activities include:

- Understand business motivations.
- Define expected business outcomes.
- Build business justification.
- Prioritize projects.

Key questions:

- Why are we moving to Azure?
- What value will the business gain?
- Which projects should be done first?

### Plan

This step creates a practical adoption plan.

Activities include:

- Assess the digital estate.
- Align stakeholders.
- Prepare skills development.
- Build a cloud adoption plan.

Key questions:

- What systems do we have today?
- Who needs to be involved?
- What skills are missing?
- What is the migration roadmap?

---

## 8. Platform Perspective

The Platform perspective focuses on preparing and securing the Azure environment.

### Ready

Ready means building the Azure foundation.

Activities include:

- Use Azure readiness guidance.
- Deploy the first landing zone.
- Expand the Azure blueprint.
- Validate best practices.

### What Is a Landing Zone?

A landing zone is a preconfigured Azure environment prepared for workloads.

It can include:

- Management Groups.
- Subscriptions.
- Virtual Networks.
- Identity integration.
- Security controls.
- Monitoring.
- Policies.

Simple idea:

```text
A landing zone is the prepared foundation where teams can safely deploy Azure workloads.
```

Key questions:

- Is Azure structured correctly?
- Are security controls in place?
- Can teams deploy resources safely?

### Govern

Govern means establishing governance and compliance.

Governance areas include:

- Cost management.
- Security baseline.
- Resource consistency.
- Regulatory compliance.
- Asset inventory.

Key Azure services used in governance:

- Azure Policy.
- Management Groups.
- Resource Locks.
- Tags.
- Microsoft Defender for Cloud.

---

## 9. Workload Perspective

The Workload perspective focuses on moving applications to Azure and building new cloud solutions.

### Adopt

Adopt includes two main approaches:

- Migrate.
- Innovate.

### Migrate

Migrate means moving existing workloads to Azure.

Examples:

- Lift and shift virtual machines.
- Database migration.
- File server migration.

### Innovate

Innovate means building new cloud-native solutions.

Examples:

- Microservices.
- Serverless applications.
- AI solutions.
- Data analytics.

---

## 10. Manage

Manage focuses on operating and supporting the Azure environment after deployment.

Operational areas include:

- Monitoring.
- Alerting.
- Backup and recovery.
- Patch management.
- Incident response.
- Capacity planning.

Key Azure services include:

- Azure Monitor.
- Log Analytics.
- Azure Backup.
- Azure Update Manager.

---

## 11. Azure Well-Architected Framework

The Azure Well-Architected Framework is used across the cloud adoption journey to design better workloads.

It helps ensure workloads are designed according to important architecture pillars.

| Pillar | Purpose |
|---|---|
| Cost Optimization | Control and reduce spending |
| Operational Excellence | Improve deployment and operations |
| Performance Efficiency | Use resources effectively |
| Reliability | Ensure availability and resiliency |
| Security | Protect systems and data |

---

## 12. Typical Cloud Adoption Journey

A typical cloud adoption journey looks like this:

```text
1. Define Strategy
2. Plan
3. Ready
4. Govern
5. Adopt
   ├── Migrate
   └── Innovate
6. Manage
7. Continuously improve using Well-Architected principles
```

---

## 13. Real-World Example: Moving an ERP System to Azure

A company wants to move its ERP system to Azure.

### Define Strategy

The company wants to:

- Reduce datacenter costs.
- Improve scalability.

### Plan

The company needs to:

- Inventory servers and databases.
- Train staff.

### Ready

The company prepares Azure by:

- Creating a landing zone.
- Configuring networking.
- Configuring identity.

### Govern

The company applies governance by:

- Applying Azure Policies.
- Setting budgets.
- Using tags.

### Adopt

The company migrates:

- ERP virtual machines.
- Databases.

### Manage

The company operates the environment by:

- Monitoring performance.
- Configuring backups.
- Configuring alerts.

### Well-Architected

The company validates:

- Security.
- Reliability.
- Cost efficiency.

---

## 14. Steps for Cloud Governance

Cloud governance is a continuous process.

It requires ongoing:

- Monitoring.
- Evaluation.
- Adjustments.

The Cloud Adoption Framework - Govern methodology divides cloud governance into five steps.

| Step | Meaning |
|---|---|
| Build a governance team | Create a team responsible for defining, maintaining, and reporting on governance policies. |
| Assess cloud risks | Identify risks related to compliance, security, operations, cost, data, resources, and AI. |
| Document cloud governance policies | Write clear rules for acceptable cloud usage and risk mitigation. |
| Enforce cloud governance policies | Use automated tools and manual oversight to apply guardrails and enforce rules. |
| Monitor cloud governance | Regularly monitor cloud usage and compliance with governance policies. |

Important idea:

```text
Governance is not a one-time task.
It must be repeated and improved over time.
```

---

## 15. Considerations for Defining a Cloud Governance Policy

When defining a corporate cloud governance policy, the key considerations are:

| Consideration | Explanation |
|---|---|
| Business risk | Document business risks and risk tolerance based on data classification and application criticality. |
| Policy and compliance | Convert risk decisions into policy statements and cloud adoption boundaries. |
| Process | Establish processes to monitor policy violations and compliance. |

---

## 16. The Five Core Disciplines of Cloud Governance

The five core disciplines of cloud governance are:

| Discipline | Purpose |
|---|---|
| Cost management | Monitor and control cloud spending. |
| Security baseline | Apply security requirements across cloud adoption efforts. |
| Resource consistency | Ensure resources are configured consistently and can be discovered, recovered, and managed. |
| Identity baseline | Enforce identity and access standards through roles and assignments. |
| Deployment acceleration | Standardize and centralize deployment practices to speed up governance adoption. |

Simple idea:

```text
Governance is not only security.
It also includes cost, identity, consistency, compliance, and deployment standards.
```

---

## 17. Useful Governance Actions with Azure Policy

Azure Policy can enforce or audit many governance requirements.

Examples:

- Allow Azure resources only in approved regions.
- Enforce geo-replication rules for data residency.
- Allow only specific VM sizes.
- Enforce consistent tags across resources.
- Recommend system updates on servers.
- Require multifactor authentication for subscription accounts.
- Require resources to send diagnostic logs to Azure Monitor Logs.

---

## 18. Azure Policy Design Objective

The main design objective of Azure Policy is to balance:

- Control and stability.
- Speed and results.

Too much control can slow teams down.

Too little control can create risk, inconsistency, and noncompliance.

Good policy design requires careful planning and testing.

Simple idea:

```text
Azure Policy should protect the environment without blocking productivity unnecessarily.
```

---

## 19. Azure Governance Hierarchy

Azure provides four main levels for governance:

```text
Management Group
└── Subscription
    └── Resource Group
        └── Resource
```

These levels define where governance settings can be applied.

Lower levels inherit settings from higher levels.

Example:

- A policy assigned at Management Group level affects subscriptions under it.
- A policy assigned at Subscription level affects resource groups and resources in that subscription.
- A policy assigned at Resource Group level affects resources inside that resource group.

---

## 20. Tenant Root Group and Management Groups

The Azure structure starts with the Tenant Root Group.

Under the Tenant Root Group, organizations can create Management Groups.

Management Groups can be nested up to six levels below the root.

Management Groups help large organizations manage:

- Multiple subscriptions.
- Access control.
- Policy assignments.
- Compliance requirements.

Simple idea:

```text
Management Groups are used to organize and govern subscriptions at scale.
```

---

## 21. Resource

A Resource is the basic building block in Azure.

Examples of resources:

- Virtual Machines.
- Virtual Networks.
- Storage Accounts.
- Databases.
- AI services.

A resource is something you create, provision, deploy, and manage in Azure.

---

## 22. Resource Groups

A Resource Group is a container for Azure resources.

When you create a resource, you must place it inside a Resource Group.

Important points:

- A Resource Group can contain many resources.
- A single resource can only belong to one Resource Group at a time.
- Actions applied to a Resource Group can affect all resources inside it.

Examples:

- Deleting a Resource Group deletes all resources inside it.
- Granting access to a Resource Group grants access to resources inside it.
- Denying access to a Resource Group denies access to resources inside it.

---

## 23. Subscriptions

An Azure Subscription is a unit of:

- Management.
- Billing.
- Scale.

Subscriptions help organize Resource Groups and manage billing.

Each subscription has limits or quotas.

Organizations can use subscriptions to manage:

- Costs.
- Teams.
- Projects.
- Environments.
- Resource ownership.

An Azure Subscription is linked to an Azure account, which is an identity in Microsoft Entra ID or a directory trusted by Microsoft Entra ID.

---

## 24. Azure Resource Manager

Azure Resource Manager is the deployment and management service for Azure.

It provides the management layer used to:

- Create resources.
- Update resources.
- Delete resources.
- Deploy templates.
- Apply RBAC.
- Audit activity.
- Monitor resources.
- Apply tags.

Simple idea:

```text
Azure Resource Manager is the central management layer for Azure resources.
```

---

## 25. Control Plane and Data Plane

Azure operations are divided into two main types:

| Plane | Purpose |
|---|---|
| Control Plane | Manage Azure resources. |
| Data Plane | Access or manipulate data inside resources. |

### Control Plane

Control Plane operations are management operations.

Examples:

- Create a Storage Account.
- Update a Virtual Network.
- Delete a VM.
- Assign a policy.
- Configure tags.

Azure Policy mainly operates in the Control Plane.

Azure Resource Manager receives Control Plane requests, authenticates them, authorizes them, and forwards them to the correct Resource Provider.

Important order:

```text
Request → Azure Resource Manager → RBAC → Azure Policy → Resource Provider
```

Important idea:

```text
If RBAC denies the request, Azure Policy is not evaluated.
```

### Data Plane

Data Plane operations access the actual data inside a resource.

Examples:

- Upload a file to Azure Storage.
- Download a blob.
- Query an SQL database.
- Read a secret from Azure Key Vault.

Data Plane requests usually go directly to the service endpoint rather than through Azure Resource Manager.

---

## 26. Azure Policy Resource Provider Modes for Data Plane

Azure Policy can also support some Data Plane scenarios through Resource Provider modes.

Examples:

| Resource Provider Mode | Used For |
|---|---|
| Microsoft.Kubernetes.Data | Managing Kubernetes clusters and components such as pods, containers, and ingresses. |
| Microsoft.KeyVault.Data | Managing vaults and certificates in Azure Key Vault. |
| Microsoft.Network.Data | Managing Azure Virtual Network Manager custom membership policies. |
| Microsoft.ManagedHSM.Data | Managing Azure Key Vault Managed HSM keys. |
| Microsoft.DataFactory.Data | Denying Azure Data Factory outbound traffic domain names. |
| Microsoft.MachineLearningServices.v2.Data | Managing Azure Machine Learning model deployments and reporting compliance. |

---

## 27. Greenfield Scenario

Greenfield means:

```text
Policy-first
```

A policy already exists before creating or updating a resource.

Example:

You create a new resource through Azure Resource Manager.

The request goes through:

1. RBAC.
2. Azure Policy.
3. Resource Provider.

If the user does not have RBAC permissions, the request fails before Azure Policy is evaluated.

If the user has RBAC permissions, Azure Policy evaluates the request.

For updates, Azure Policy needs the full target state.

So Azure Policy:

1. Reads the current resource state.
2. Merges it with the requested changes.
3. Evaluates the final target state against policy rules.

---

## 28. Brownfield Scenario

Brownfield means:

```text
Resource-first
```

Resources already exist, and then a new policy is assigned to them.

In Brownfield scenarios, evaluation happens through compliance scans.

Important points:

- Compliance scans run automatically every 24 hours.
- Compliance scans can be triggered manually.
- Existing noncompliant resources are not automatically deleted.
- Existing resources are marked as noncompliant if they violate the new policy.
- Future resource creation or updates can be blocked depending on the policy effect.

Example:

A policy allows resources only in West Europe.

Existing resources outside West Europe:

- Are not deleted.
- Are marked as noncompliant.

New resources outside West Europe:

- Are denied if the policy effect is deny.

---

## 29. Azure Policy Resources

Azure Policy has six important resource types:

| Azure Policy Resource | Purpose |
|---|---|
| Definitions | Describe what is checked and what effect happens. |
| Initiatives | Group multiple policy definitions together. |
| Assignments | Apply a policy or initiative to a scope. |
| Exemptions | Exclude resources from policy evaluation or provide temporary waivers. |
| Attestations | Manually confirm compliance for manual policies. |
| Remediations | Bring noncompliant resources into compliance. |

---

## 30. Definitions

Azure Policy definitions describe:

- Resource compliance conditions.
- The effect to take when conditions are met.

Simple idea:

```text
A policy definition is the actual governance rule.
```

A definition may include:

- Conditions.
- Effects.
- Parameters.
- Policy rules.

Example:

```text
Only allow resources in approved Azure regions.
```

---

## 31. Initiatives

An initiative is a group of related policy definitions.

Simple idea:

```text
Initiative = policy set
```

Initiatives simplify assignment and management.

Instead of assigning many policies one by one, you assign one initiative.

Example:

A tagging initiative may include policies that require:

- CostCenter tag.
- Owner tag.
- Environment tag.
- Application tag.

---

## 32. Built-in Policy and Built-in Initiative

A built-in policy is provided and maintained by Microsoft.

A built-in initiative is a group of built-in policy definitions.

Built-in policies and initiatives help with:

- Security best practices.
- Regulatory compliance.
- Industry standards.
- Common Azure governance needs.

---

## 33. Custom Policy and Custom Initiative

A custom policy is created by the customer when built-in policies do not meet specific requirements.

A custom initiative is a group of custom policy definitions.

Custom policies are useful when an organization needs specific rules that match its own environment.

Example:

```text
Require every resource in production to have BusinessOwner, CostCenter, and DataClassification tags.
```

---

## 34. Microsoft for Sovereignty Initiatives

Microsoft for Sovereignty initiatives and compliance mappings extend Azure built-in initiatives.

They help organizations:

- Automate policy enforcement.
- Reduce risk of noncompliance.
- Strengthen data protection.
- Support sovereignty and regulatory requirements.
- Build a stronger governance framework.

---

## 35. Assignments

A policy assignment defines where a policy or initiative applies.

A policy or initiative can be assigned to:

- Management Group.
- Subscription.
- Resource Group.

Policy assignments can be created through:

- Azure Portal.
- API.
- Azure CLI.
- PowerShell.

Simple idea:

```text
Definition = the rule
Assignment = where the rule is applied
```

---

## 36. Definition Location vs Assignment Scope

Policy and initiative definitions are stored at a definition location.

The definition location can be:

- Management Group.
- Subscription.

The definition location determines where the policy or initiative can be assigned.

The assignment scope determines which resources are evaluated.

Simple example:

```text
If a policy definition is stored at a Management Group, it can be assigned to that Management Group or lower scopes.
```

---

## 37. Optional Assignment Settings

Policy assignments can include optional settings.

| Setting | Purpose |
|---|---|
| Resource selectors | Allow gradual rollout based on location or resource type. |
| Overrides | Change the effect of a policy without changing the original definition. |
| enforcementMode | Test policy results without enforcing the effect. |
| Excluded scopes | Exclude inner scopes or resources from assignment. |
| Noncompliance messages | Explain why a resource is noncompliant. |
| Parameters | Provide values during assignment. |
| Managed identity | Required for remediation actions such as deployIfNotExists. |

---

## 38. Exemptions

Policy exemptions are used to exempt a resource or resource hierarchy from policy evaluation.

Exempt resources count toward overall compliance, but they are not evaluated in the normal way.

Exemptions are created after assignment, not during assignment.

Two exemption categories exist:

| Exemption Type | Meaning |
|---|---|
| Mitigated | The policy intent is met through another method. |
| Waiver | The noncompliance is temporarily accepted. |

Simple example:

```text
A resource is noncompliant with a policy, but the organization accepts it temporarily because a migration is in progress.
```

---

## 39. Attestations

Attestations are used with manual policies.

They allow compliance to be manually confirmed for resources or scopes.

Simple idea:

```text
Attestation = manual confirmation of compliance
```

This is useful when Azure Policy cannot automatically determine compliance.

---

## 40. Remediations

Remediation tasks bring noncompliant resources into compliance.

They are used with policies that have effects such as:

- modify.
- deployIfNotExists.

Examples:

- Add a missing tag.
- Deploy missing diagnostic settings.
- Correct a resource configuration.

Simple idea:

```text
Remediation fixes resources after Azure Policy detects noncompliance.
```

---

## 41. Azure Policy Definitions

Azure Policy definitions describe what Azure Policy checks and what happens when the rule is matched.

A definition includes:

- Conditions.
- Effects.
- Parameters.
- Policy rules.

The main idea is that the policy definition is the actual governance rule.

Example:

```text
If a resource is not in an allowed location, deny creation.
```

---

## 42. Anatomy of a Policy Definition

Azure Policy definitions are written in JSON.

The most important part is `policyRule` because it contains the actual logic.

Simple pattern:

```text
if this condition is true,
then apply this effect.
```

| Element | Simple Explanation |
|---|---|
| displayName | The readable name of the policy. |
| description | Explains what the policy does and when it should be used. |
| policyType | Shows where the policy comes from: BuiltIn, Custom, or Static. |
| mode | Defines what kind of resources or properties the policy evaluates, such as All, Indexed, or Resource Provider modes. |
| version | Tracks policy versions, especially for built-in policies. If no version is specified, Azure uses the latest version. |
| metadata | Stores extra information such as version, category, preview status, or deprecated status. |
| parameters | Makes policies reusable by allowing different values during assignment. |
| policyRule | Contains the main logic of the policy using if and then. |

---

## 43. Example: Allowed Locations Policy

The example policy was called:

```text
Allowed locations
```

Purpose:

```text
Restrict the Azure regions where resources can be deployed.
```

The policy checks whether the resource location is not in the allowed list.

If the resource is being deployed to a non-allowed location, the effect is:

```text
deny
```

Important exclusions in the example:

- Resource Groups.
- Microsoft.AzureActiveDirectory/b2cDirectories.
- Resources using the global region.

Why b2cDirectories are excluded:

Their location field is not a normal Azure region. It can be values such as:

- United States.
- Europe.
- Asia Pacific.
- Australia.

Simple idea:

```text
Allowed locations policy helps enforce geo-compliance and data residency requirements.
```

---

## 44. Logical Operators and Conditions

The `if` block defines the conditions used to evaluate resources.

Azure Policy supports logical operators.

| Operator | Simple Explanation |
|---|---|
| not | Reverses the condition result. |
| allOf | Works like AND. All conditions must be true. |
| anyOf | Works like OR. One or more conditions must be true. |

Simple example:

```text
allOf means:
Condition 1 must be true
AND Condition 2 must be true
AND Condition 3 must be true
```

Nested logical operations are also possible.

Example:

```text
allOf can contain a not condition inside it.
```

---

## 45. Conditions in Azure Policy

Conditions evaluate resource properties, values, or counts.

| Type | Meaning |
|---|---|
| Field | Evaluates resource properties such as type, location, tags, ID, or aliases. |
| Value | Evaluates a specific value or expression. |
| Count | Counts how many members of an array meet a condition. |

Common fields include:

- name.
- type.
- location.
- tags.
- identity.type.
- resource ID.
- property aliases.

Common evaluation criteria include:

- equals.
- notEquals.
- like.
- notLike.
- contains.
- notContains.
- in.
- notIn.
- containsKey.
- exists.
- less.
- greater.

Important note:

If a function inside the policy causes an error, the policy can result in a deny effect. During testing, this risk can be reduced by using enforcementMode Disabled.

---

## 46. Policy Functions

Policy functions add extra logic to policy rules.

They can be used inside:

- Policy rules.
- Parameter values in initiatives.

Important functions include:

| Function | Purpose |
|---|---|
| addDays() | Adds days to a date/time value. |
| field() | Retrieves a field value from the evaluated resource. |
| requestContext().apiVersion | Returns the API version that triggered evaluation. |
| policy() | Returns information about the policy being evaluated. |
| ipRangeContains() | Checks whether an IP range contains another IP range. |
| current() | Used inside count expressions to refer to the current array item. |
| utcNow() | Returns the current date and time in ISO 8601 format. |

Simple idea:

```text
Functions make policy rules more dynamic and intelligent.
```

---

## 47. Effect Types — then Blocks

The `then` block defines the policy effect.

The effect determines what Azure Policy does when the condition is matched.

| Effect | Simple Explanation |
|---|---|
| disabled | Turns off the policy. The policy is not active. |
| append | Adds fields to a resource request. It is less commonly used now because modify can handle many similar scenarios. |
| modify | Adds, updates, or removes properties or tags. Commonly used to automatically correct resources. |
| deny | Blocks a resource request if it does not meet policy requirements. |
| denyAction | Blocks a specific action. Currently, the supported action is DELETE. |
| audit | Records noncompliance but does not block the request. Useful for monitoring and testing. |
| auditIfNotExists | Checks whether a related resource or configuration exists. If not, Azure Policy audits the resource. |
| deployIfNotExists | Deploys missing resources or configurations. Useful for remediation and automation. |
| manual | Allows compliance to be confirmed manually when it cannot be fully checked automatically. |

Simple pattern:

| Stage | Recommended Effect |
|---|---|
| First test | audit |
| Enforce later | deny, modify, or deployIfNotExists |
| Turn off policy | disabled |
| Manual confirmation needed | manual |

Important note:

```text
manual is not interchangeable with the other effects because it depends on manual attestation.
```

---

## 48. Synchronous vs Asynchronous Effects

Azure Policy effects can be synchronous or asynchronous.

| Type | Meaning | Examples |
|---|---|---|
| Synchronous evaluation | Happens during the resource request. It can block or modify the request immediately. | deny, modify, append, disabled |
| Asynchronous evaluation | Happens after evaluation and does not directly block the request. | audit, auditIfNotExists, deployIfNotExists |
| Manual attestation | Compliance is manually confirmed. | manual |

Simple idea:

```text
deny stops the request immediately.
audit only records the issue.
modify can correct the request.
deployIfNotExists can deploy missing configuration.
```

---

## 49. Multiple Policies on One Resource

Multiple policies can apply to the same resource.

They can be assigned at:

- Same scope.
- Different scopes.

Each policy is evaluated independently.

The final result is cumulative and most restrictive.

Simple idea:

```text
If one policy allows something but another policy denies it, the more restrictive result wins.
```

---

## 50. Evaluation of Resources Through Azure Policy

Azure Policy evaluates resources to determine whether they are compliant.

Azure Policy can evaluate:

- Existing resources.
- Newly created resources.
- Updated resources.

Azure Policy provides insight and control over resources in:

- Subscriptions.
- Management Groups of subscriptions.

It can be used to:

- Prevent resources from being created in wrong locations.
- Enforce consistent tag usage.
- Audit existing resources.
- Check appropriate configurations and settings.

---

## 51. Evaluation Triggers

Azure Policy evaluations happen because of specific events.

Common triggers include:

- A policy or initiative is newly assigned to a scope.
- An assigned policy or initiative is updated.
- A resource is deployed.
- A resource is updated.
- A subscription is created or moved in a Management Group hierarchy.
- A policy exemption is created, updated, or deleted.
- Machine configuration compliance details are updated.
- An on-demand scan is triggered.

Simple idea:

```text
Azure Policy evaluation happens when policies change, resources change, scopes change, or scans run.
```

---

## 52. Evaluation Timing

Compliance scans can happen automatically or manually.

| Scan Type | Explanation |
|---|---|
| Automatic full scan | Runs automatically every 24 hours. |
| Manual scan | Can be triggered manually, especially useful in Brownfield scenarios. |

Manual scan command:

```bash
az policy state trigger-scan
```

When a new policy is assigned, there can be a delay before it takes effect.

The delay can be up to 30 minutes because of Azure Resource Manager cache.

To bypass the cache delay:

```text
Sign out and sign back in.
```

---

## 53. Factors That Affect Compliance Scan Duration

Compliance scan duration can be affected by:

| Factor | Explanation |
|---|---|
| Policy definition complexity | Larger or more complex definitions take longer to evaluate. |
| Number of policies | More policies can increase scan time. |
| Scope size | Larger scopes with more resources take longer. |
| System load | Compliance scans are low-priority operations, so they may be delayed. |
| Synchronous scan behavior | Scans can take several minutes or tens of minutes even in smaller environments. |

Important idea:

```text
Compliance scan timing is not always immediate or predictable.
```

---

## 54. Resource Compliance States

When policies or initiatives are assigned, Azure Policy determines which resources are applicable and then evaluates them.

Possible compliance states include:

| State | Meaning |
|---|---|
| Non-compliant | The resource does not meet policy requirements. |
| Compliant | The resource meets policy requirements. |
| Error | A template or evaluation error occurred. |
| Conflicting | Two or more policy assignments conflict with each other. |
| Protected | The resource is protected by a denyAction assignment. |
| Exempted | The resource has an exemption. |
| Unknown | Default state for definitions with manual effect. |

Simple example of conflict:

```text
Two policies try to append the same tag with different values.
```

---

## 55. Compliance Percentage

Compliance percentage is calculated using:

```text
Compliant + Exempt + Unknown resources
--------------------------------------
Total resources
```

Total resources include:

- Compliant.
- Non-compliant.
- Unknown.
- Exempt.
- Conflicting.
- Error.

Important idea:

```text
Exempt and Unknown resources can count toward the compliance percentage.
```

---

## 56. Enforcement Mode

enforcementMode is a property of a policy assignment.

It allows you to test a policy without enforcing its effect.

This is useful for safe testing.

With enforcementMode Disabled:

- The policy is evaluated.
- Compliance results are shown.
- The policy effect is not enforced.
- No Azure Activity Log entry is triggered for the blocked action.

Simple idea:

```text
enforcementMode Disabled = evaluate but do not enforce.
```

---

## 57. enforcementMode vs disabled Effect

These two are different.

| Feature | Meaning |
|---|---|
| disabled effect | The policy is turned off and resource evaluation does not happen. |
| enforcementMode Disabled | Evaluation still happens, but the effect is not enforced. |

Simple comparison:

```text
disabled effect = do not evaluate
enforcementMode Disabled = evaluate only, do not enforce
```

---

## 58. enforcementMode Values

| Mode | JSON Value | Meaning |
|---|---|---|
| Enabled | Default | The policy effect is enforced during resource creation or update. |
| Disabled | DoNotEnforce | The policy effect is not enforced during resource creation or update. |

Important note:

Remediation tasks can still be started for deployIfNotExists policies even when enforcementMode is set to DoNotEnforce.

---

## 59. Policy Enforcement and Safe Deployment Best Practices

Applying policies directly to production can cause unintended behavior if the policies are not tested.

Best practice:

```text
Treat policy as code.
```

Policy as Code means:

- Store policy definitions in source control.
- Test policy changes.
- Validate changes before production.
- Automate testing.
- Reduce manual errors.

The safe deployment framework focuses on:

- Minimizing policy change impact.
- Ensuring compliance.
- Avoiding disruption to production workloads.

---

## 60. Safe Deployment Step 1 — Start with enforcementMode Disabled

When assigning new policies, especially policies with deny or modify effects, start with:

```text
enforcementMode Disabled
```

This allows you to:

- View compliance state.
- Understand policy impact.
- Test without blocking operations.
- Detect issues before enforcement.
- Avoid disrupting existing workloads.

This is commonly called a:

```text
What If scenario
```

---

## 61. Safe Deployment Step 2 — Use Deployment Rings

Policies should be deployed gradually using deployment rings.

Recommended rollout:

```text
Test → Development → Small production subset → Larger production scope → Full production
```

Deployment rings help:

- Reduce risk.
- Detect issues early.
- Validate policy behavior.
- Control negative impact.
- Expand safely.

Simple idea:

```text
Do not apply a new strong policy everywhere at once.
Deploy it gradually.
```

---

## 62. Safe Deployment Process

A safe Azure Policy deployment process includes:

| Step | Explanation |
|---|---|
| Create definition | Define the policy, often at root or high-level scope. |
| Create assignment | Assign the policy to a limited scope or ring. |
| Use enforcementMode Disabled | Evaluate compliance without enforcing changes. |
| Compliance check | Confirm the policy evaluates resources correctly. |
| Application health check | Confirm the policy does not break workloads. |
| Repeat for non-production | Test across nonproduction rings first. |
| Enable enforcement | Turn enforcement on after validation. |
| Repeat for production rings | Gradually deploy to production scopes. |

---

## 63. Reacting to Policy State Changes

Azure Policy events allow applications to react when policy states change.

This avoids the need for:

- Complicated code.
- Expensive polling.
- Inefficient polling services.

Flow:

```text
Azure Policy event → Azure Event Grid → Event Handler
```

---

## 64. Azure Event Grid

Azure Event Grid delivers events reliably to applications.

It provides:

- Retry policies.
- Dead-letter delivery.
- Event routing.
- Event filtering.
- Event multicasting.

Simple idea:

```text
Event Grid sends policy state change events to systems that need to react.
```

---

## 65. Event Handlers

An Event Handler is the destination that receives and processes the event.

Examples:

- Azure Functions.
- Azure Logic Apps.
- Custom HTTP listener.
- Webhooks.

Example use case:

```text
When a resource becomes noncompliant, Azure Policy can send an event through Event Grid, and Azure Functions can trigger an automated action.
```

---

## 66. Check Your Knowledge — Recap

Azure Policy assesses compliance at scale and enforces organizational and regulatory standards across Azure environments.

It can help with things like:

- Allowed VM sizes.
- System update recommendations.
- MFA requirements.
- Allowed regions.
- Required tags.
- Diagnostic logging.

The two recommended safe deployment steps are:

- Start with Enforcement Mode Disabled.
- Deploy policies in deployment rings.

This provides a controlled rollout.

The purpose of Enforcement Mode is to test policy outcomes without initiating the policy effect.

It is used for safe testing.

Azure Resource Manager is the deployment and management service for Azure.

It allows:

- Creation of Azure resources.
- Update of Azure resources.
- Deletion of Azure resources.

Azure Policies can be assigned at these levels:

- Management Group.
- Subscription.
- Resource Group.

---

## 67. Module Summary

Azure Policy is a key part of the governance model in the Cloud Adoption Framework for Azure.

It helps balance:

- Control and stability.
- Speed and results.

Azure Policy helps organizations:

- Enforce organizational standards.
- Enforce regulatory standards.
- Assess compliance at scale.
- Manage current and future Azure resources.
- Apply governance guardrails.
- Prevent or detect noncompliance.
- Remediate some noncompliant resources.

Main lesson:

```text
Azure Policy should be designed carefully, tested safely, and deployed gradually.
The goal is to enforce governance without disrupting operations.
```
