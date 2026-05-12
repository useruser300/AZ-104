# Microsoft Entra ID

## 1. Introduction to Microsoft Entra ID

Microsoft Entra ID is a cloud-based identity and access management service provided by Microsoft.

It is used to manage identities, enforce access policies, and secure access to applications and data in both cloud and on-premises environments.

The learning module introduced the following main goals:

## Describe Microsoft Entra ID

Microsoft Entra ID is Microsoft’s cloud identity platform.

It provides authentication, authorization, policy enforcement, and identity protection for:

- Users
- Devices
- Applications
- Cloud resources
- On-premises integrated resources

## Compare Microsoft Entra ID with Active Directory Domain Services

The module explained that Microsoft Entra ID and Active Directory Domain Services share some identity-related concepts, but they are not the same service.

AD DS is traditional, Windows Server-based, domain-oriented directory infrastructure.

Microsoft Entra ID is a cloud-native identity and access management service designed mainly for internet-based and cloud-based applications.

## Describe Microsoft Entra ID as a Directory for Cloud Apps

Microsoft Entra ID acts as a central cloud directory for Microsoft cloud services such as:

- Microsoft 365
- Azure
- Microsoft Dynamics 365
- Microsoft Intune

It allows organizations to use one identity system across many Microsoft cloud services instead of maintaining separate directories for each service.

## Describe Microsoft Entra ID P1 and P2

The module explained that Microsoft Entra ID has different licensing tiers.

The Free version provides basic identity services.

Microsoft Entra ID P1 and P2 provide more advanced identity, access, security, and governance features.

P2 includes advanced protection and privileged identity capabilities that are not included in P1.

## Describe Microsoft Entra Domain Services

Microsoft Entra Domain Services provides managed domain services in Azure.

It supports traditional domain features such as:

- LDAP
- Kerberos authentication
- NTLM authentication
- Group Policy
- Domain Join

It is useful for legacy applications that require traditional AD DS-style authentication but are running in the cloud.

---

# 2. What Active Directory Domain Services Is

Active Directory Domain Services, also known as AD DS or traditionally just Active Directory, is a directory service.

It stores directory data such as:

- User accounts
- Passwords
- Groups
- Computer accounts
- Domain objects

It makes this data available to:

- Network users
- Administrators
- Devices
- Services

AD DS runs on Windows Server.

A Windows Server that runs AD DS is called a Domain Controller.

AD DS is mainly designed for on-premises enterprise environments.

---

# 3. What Microsoft Entra ID Is

Microsoft Entra ID is part of Microsoft’s Platform as a Service offering.

It operates as a Microsoft-managed cloud directory service.

It is not infrastructure that the customer owns and manages directly.

It is also not Infrastructure as a Service.

This means:

- You have less control over the internal implementation.
- You do not need to deploy, maintain, patch, or manage domain controllers yourself.
- Microsoft manages the service infrastructure.

Microsoft Entra ID provides features that are not natively available in traditional AD DS, such as:

- Multi-factor authentication
- Identity protection
- Self-service password reset
- Conditional Access
- Cloud application access management

---

# 4. What Microsoft Entra ID Can Be Used For

Microsoft Entra ID can be used to provide secure access to cloud-based resources for organizations and individuals.

The main use cases covered were:

## Configuring Access to Applications

Microsoft Entra ID can control who is allowed to access cloud applications.

## Configuring Single Sign-On to SaaS Applications

It can provide Single Sign-On for cloud-based SaaS applications.

This means users can sign in once and access multiple integrated applications.

## Managing Users and Groups

Administrators can create, manage, and organize users and groups.

## Provisioning Users

Microsoft Entra ID can help automate user account creation and assignment.

## Enabling Federation Between Organizations

It can support federation scenarios where organizations trust identities from other organizations or identity providers.

## Providing an Identity Management Solution

It acts as a central identity platform for cloud services.

## Identifying Irregular Sign-In Activity

It can detect suspicious or unusual sign-in behavior.

## Configuring Multi-Factor Authentication

It supports MFA to strengthen login security.

## Extending On-Premises Active Directory to Microsoft Entra ID

Organizations can connect existing AD DS environments to Microsoft Entra ID using tools such as Microsoft Entra Connect.

## Configuring Application Proxy

Application Proxy allows secure access to cloud and local applications.

## Configuring Conditional Access

Conditional Access allows access decisions based on conditions such as:

- User
- Device
- Location
- Risk level
- Application
- Sign-in behavior

---

# 5. Microsoft Entra as a Separate Azure Service

Microsoft Entra is a separate Azure service.

The most basic Microsoft Entra ID tier is included automatically with new Azure subscriptions.

This basic version is referred to as the Free tier.

If an organization subscribes to Microsoft cloud business services such as:

- Microsoft 365
- Microsoft Intune
- Azure
- Dynamics CRM Online

then it automatically uses Microsoft Entra ID.

Every tenant is automatically a Microsoft Entra tenant.

---

# 6. Default Directory in Azure

When you create a new Azure subscription using a Microsoft account, the subscription automatically includes a new Microsoft Entra tenant.

This tenant is usually named:

```text
Default Directory
```

This tenant becomes the identity directory associated with the Azure subscription.

---

# 7. Microsoft Entra ID Is Not the Same as Deploying AD DS in Azure

A very important point covered was that implementing Microsoft Entra ID is not the same as deploying virtual machines in Azure, installing AD DS, and creating domain controllers.

These are different models.

## Deploying AD DS in Azure

This means:

- You create Azure virtual machines.
- You install Windows Server.
- You install the AD DS role.
- You promote the server to a Domain Controller.
- You manage it like traditional Active Directory.

## Using Microsoft Entra ID

This means:

- You use Microsoft’s managed cloud identity service.
- You do not manage domain controllers.
- You use cloud identity features.
- You manage users, groups, apps, authentication, authorization, and policies through Microsoft Entra.

Microsoft Entra ID is much more focused on web-based, SaaS, and cloud identity scenarios.

AD DS is more focused on traditional on-premises domain-based applications.

---

# 8. Microsoft Entra Tenants

Microsoft Entra ID is multi-tenant by design.

This means Microsoft Entra hosts many separate directory instances while keeping them isolated from one another.

A tenant usually represents a company or organization that subscribes to a Microsoft cloud service such as:

- Microsoft 365
- Intune
- Azure

From a technical perspective, a tenant is an individual Microsoft Entra instance.

Within an Azure subscription, it is possible to create multiple Microsoft Entra tenants.

This can be useful for testing Microsoft Entra features in one tenant without affecting another tenant.

---

# 9. Azure Subscription and Microsoft Entra Tenant Relationship

At any given time, an Azure subscription must be associated with one and only one Microsoft Entra tenant.

This association allows permissions to be granted to Azure resources using RBAC.

RBAC permissions can be assigned to:

- Users
- Groups
- Applications

These identities must exist in the Microsoft Entra tenant associated with that Azure subscription.

However, the same Microsoft Entra tenant can be associated with multiple Azure subscriptions.

This allows the same users, groups, and applications to manage resources across multiple Azure subscriptions.

---

# 10. Microsoft Entra Tenant Domain Names

Each Microsoft Entra tenant receives a default DNS domain name.

The format is usually:

```text
prefix.onmicrosoft.com
```

Example:

```text
contoso.onmicrosoft.com
```

The prefix can come from the Microsoft account name used to create the Azure subscription or can be explicitly chosen when creating the tenant.

Organizations can also add custom domain names to the same tenant.

Example:

```text
company.com
```

The Microsoft Entra tenant acts as:

- A security boundary
- A container for Microsoft Entra objects

Examples of Microsoft Entra objects include:

- Users
- Groups
- Applications

A single Microsoft Entra tenant can support multiple Azure subscriptions.

---

# 11. Microsoft Entra Schema

The Microsoft Entra schema contains fewer object types than the AD DS schema.

A major difference is that Microsoft Entra ID does not include the traditional AD DS computer class in the same way.

It includes a device class, but joining devices to Microsoft Entra ID is different from joining computers to AD DS.

Microsoft Entra schema is also easily extensible.

Its extensions are fully reversible.

This differs from AD DS schema extensions, which are traditionally more sensitive and not easily reversible.

---

# 12. Microsoft Entra ID and the Lack of Traditional Computer Domain Membership

Microsoft Entra ID does not support traditional computer domain membership in the same way AD DS does.

Because of this, you cannot use Microsoft Entra ID to manage computers and user settings using traditional AD DS techniques such as Group Policy Objects.

Instead, Microsoft Entra ID follows a modern management model.

Its main strengths are:

- Providing directory services
- Storing user data
- Storing device data
- Storing application data
- Publishing identity information
- Handling authentication
- Handling authorization

This model is used heavily by cloud services such as Microsoft 365.

---

# 13. Microsoft Entra ID Does Not Use Organizational Units

Microsoft Entra ID does not include the Organizational Unit class.

This means you cannot arrange Microsoft Entra objects into a custom hierarchy of OUs like in AD DS.

In AD DS, OUs are commonly used for:

- Group Policy scoping
- Delegated administration
- Organizational structure

In Microsoft Entra ID, equivalent organization is usually done through:

- Groups
- Roles
- Administrative units
- Access assignments
- Policies

The module specifically emphasized that the lack of OUs is not a major shortcoming because OUs in AD DS are mainly used for Group Policy and delegation, while Microsoft Entra ID uses other models.

---

# 14. Applications and Service Principals in Microsoft Entra ID

Applications in Microsoft Entra ID are represented by two important object types:

## Application Object

The Application object contains the application definition.

It describes the app globally.

## Service Principal Object

The servicePrincipal object represents an instance of the application inside a specific Microsoft Entra tenant.

This separation allows one application to be defined in one tenant and used across multiple tenants.

For each tenant where the application is used, a service principal object is created.

Microsoft Entra ID creates the service principal when the corresponding application is registered in that tenant.

---

# 15. Comparing Microsoft Entra ID and AD DS

Microsoft Entra ID can be viewed as the cloud-based counterpart of AD DS, but they are not the same.

They share some identity concepts, but they have major differences in architecture, protocol usage, management model, and target scenarios.

---

# 16. Characteristics of AD DS

AD DS is the traditional Windows Server-based Active Directory deployment.

It can run on:

- Physical servers
- Virtual servers

AD DS is part of the larger Windows Active Directory technology family.

That family includes:

- Active Directory Domain Services
- Active Directory Certificate Services
- Active Directory Lightweight Directory Services
- Active Directory Federation Services
- Active Directory Rights Management Services

Important AD DS characteristics:

## AD DS Is a True Directory Service

AD DS uses a hierarchical structure based on X.500 concepts.

## AD DS Uses DNS

AD DS uses DNS to locate resources such as domain controllers.

## AD DS Uses LDAP

AD DS can be queried and managed using LDAP calls.

## AD DS Uses Kerberos

AD DS primarily uses the Kerberos protocol for authentication.

## AD DS Uses OUs and GPOs

Organizational Units and Group Policy Objects are central to AD DS management.

## AD DS Includes Computer Objects

Computers that join an Active Directory domain are represented as computer objects.

## AD DS Uses Trusts

Trusts between domains allow delegated management and cross-domain authentication scenarios.

---

# 17. Deploying AD DS on Azure Virtual Machines

It is possible to deploy AD DS on Azure virtual machines.

This can provide scalability and availability for an on-premises AD DS environment.

However, deploying AD DS on Azure virtual machines does not mean you are using Microsoft Entra ID.

It is still traditional AD DS running on virtual machines.

A key note covered:

When deploying AD DS on an Azure virtual machine, you should not use the C drive for AD DS storage.

You need one or more additional Azure data disks for:

- AD DS database
- Logs
- SYSVOL folder

The Host Cache Preference setting for those disks should be set to:

```text
None
```

---

# 18. Characteristics of Microsoft Entra ID

Microsoft Entra ID has similarities with AD DS, but it is different in important ways.

Using Microsoft Entra ID is not the same as deploying an Active Directory Domain Controller on an Azure virtual machine.

Important Microsoft Entra ID characteristics:

## Microsoft Entra ID Is Primarily an Identity Solution

It is designed for internet-based applications.

It commonly uses:

- HTTP on port 80
- HTTPS on port 443

## Microsoft Entra ID Is Multi-Tenant

It is designed as a multi-tenant cloud directory service.

## Microsoft Entra ID Uses a Flat Structure

Users and groups are created in a flat structure.

There are no traditional OUs or GPOs.

## Microsoft Entra ID Does Not Use LDAP Queries

You cannot query Microsoft Entra ID using LDAP in the same way as AD DS.

Instead, Microsoft Entra ID uses REST APIs over HTTP and HTTPS.

## Microsoft Entra ID Does Not Use Kerberos as Its Primary Authentication Model

Instead, it uses modern web authentication and authorization protocols.

Examples include:

- SAML
- WS-Federation
- OpenID Connect
- OAuth

## Microsoft Entra ID Includes Federation Services

Many third-party services can federate with and trust Microsoft Entra ID.

Examples include services such as Facebook and other identity providers.

---

# 19. Microsoft Entra ID as a Directory Service for Cloud Apps

When organizations deploy cloud services such as Microsoft 365 or Intune, they need cloud directory services to provide authentication and authorization.

Each cloud service that needs authentication may use a Microsoft Entra tenant.

When an organization uses more than one cloud service, it is much more convenient to use a single cloud directory instead of separate directories for each service.

Microsoft Entra ID can act as one identity service for Microsoft cloud services such as:

- Microsoft 365
- Azure
- Microsoft Dynamics 365
- Intune

Microsoft Entra ID provides developers with centralized authentication and authorization for Azure applications.

It can also integrate with:

- Other identity providers
- On-premises AD DS

Microsoft Entra ID can provide users with Single Sign-On experiences for applications and services such as:

- Facebook
- Google services
- Yahoo
- Microsoft cloud services

---

# 20. Microsoft Entra ID Support for Custom Applications

Implementing Microsoft Entra ID support for custom applications can be complex.

However, tools such as:

- Azure portal
- Microsoft Visual Studio 2013 and later

make the configuration process more straightforward.

For Azure App Service Web Apps, Microsoft Entra authentication can be enabled directly from the Authentication/Authorization blade in the Azure portal.

By selecting the Microsoft Entra tenant, administrators can ensure that only users with accounts in that directory can access the website.

Different authentication settings can also be applied to individual deployment slots.

---

# 21. Microsoft Entra ID P1 and P2 Plans

Microsoft Entra ID P1 and P2 provide extra functionality compared with the Free and Office 365 editions.

Premium versions require additional licensing cost per user.

Microsoft Entra ID premium comes in two main versions:

- Microsoft Entra ID P1
- Microsoft Entra ID P2

They can be purchased as:

- Extra standalone licenses
- Part of Microsoft Enterprise Mobility + Security

Microsoft Enterprise Mobility + Security can also include licenses for:

- Azure Information Protection
- Microsoft Intune

Microsoft provides a free trial period that can be used to experience the full functionality of Microsoft Entra ID P2.

---

# 22. Microsoft Entra ID P1 Features

Microsoft Entra ID P1 includes several advanced features.

## Self-Service Group Management

This simplifies group administration.

Users can be given rights to create and manage groups.

End users can request to join groups.

Group owners can approve requests and manage group memberships.

## Advanced Security Reports and Alerts

Administrators can monitor and protect access to cloud applications.

They can view detailed logs showing:

- Advanced anomalies
- Inconsistent access patterns
- Potential security issues

These reports are machine learning based.

They help improve access security and respond to potential threats.

## Multi-Factor Authentication

Full MFA works with:

- On-premises applications using VPN, RADIUS, and others
- Azure
- Microsoft 365
- Dynamics 365
- Third-party Microsoft Entra gallery applications

The module noted that full MFA does not work with some non-browser off-the-shelf applications such as Microsoft Outlook in the described context.

## Microsoft Identity Manager Licensing

Microsoft Identity Manager integrates with Microsoft Entra ID P1 or P2 to provide hybrid identity solutions.

MIM can bridge multiple on-premises authentication stores such as:

- AD DS
- LDAP
- Oracle
- Other applications

This provides consistent identity experiences for:

- On-premises line-of-business applications
- SaaS solutions

## Enterprise SLA of 99.9 Percent

Microsoft guarantees at least 99.9% availability for Microsoft Entra ID P1 or P2.

The same SLA also applies to Microsoft Entra Basic.

## Password Reset with Writeback

Self-service password reset can follow the on-premises Active Directory password policy.

Password writeback allows cloud password reset changes to be written back to on-premises AD DS.

## Cloud App Discovery

This feature discovers the most frequently used cloud-based applications.

## Conditional Access Based on Device, Group, or Location

Conditional Access allows administrators to configure access for critical resources based on several criteria, such as:

- Device
- Group
- Location

## Microsoft Entra Connect Health

Microsoft Entra Connect Health provides operational insight into Microsoft Entra ID and hybrid identity components.

It works with:

- Alerts
- Performance counters
- Usage patterns
- Configuration settings

Collected information is shown in the Microsoft Entra Connect Health portal.

---

# 23. Microsoft Entra ID P2 Features

Microsoft Entra ID P2 includes the P1 features and adds extra functionality.

## Microsoft Entra ID Protection

This feature provides enhanced functionality for monitoring and protecting user accounts.

Administrators can define:

- User risk policies
- Sign-in risk policies

They can also review user behavior and flag users as risky.

## Microsoft Entra Privileged Identity Management

Privileged Identity Management allows organizations to configure additional security controls for privileged users, such as administrators.

With PIM, administrators can define:

- Permanent administrators
- Temporary administrators
- Policy workflows

These workflows activate when someone wants to use administrative privileges to perform a task.

PIM helps enforce just-in-time and controlled privileged access.

---

# 24. Important Note About Microsoft Entra Plans

Plans and licensing options change frequently.

The module explicitly noted that current plans and capabilities should be checked on Microsoft’s website.

---

# 25. Microsoft Entra Domain Services

Microsoft Entra Domain Services is a managed domain service.

It is useful when organizations have line-of-business applications that expect traditional domain services.

Many existing business applications are deployed on computers and devices that are domain members.

These applications often use:

- AD DS-based credentials
- Group Policy
- Kerberos authentication
- NTLM authentication
- LDAP

When moving these applications to Azure, organizations need a way to provide authentication services.

---

# 26. Options for Supporting Legacy Domain-Based Applications in Azure

The module discussed two traditional options:

## Site-to-Site VPN

An organization can implement a site-to-site VPN between local infrastructure and Azure IaaS.

In this model, authentication traffic crosses the VPN.

## Replica Domain Controllers in Azure

An organization can deploy replica domain controllers from local AD DS as virtual machines in Azure.

In this model:

- Replication traffic crosses the VPN.
- Authentication traffic stays in the cloud.

Both approaches can involve:

- Extra cost
- Extra administration
- More operational complexity

---

# 27. Microsoft Entra Domain Services as an Alternative

Microsoft provides Microsoft Entra Domain Services as an alternative to those approaches.

It runs as part of Microsoft Entra ID P1 or P2.

It provides domain services such as:

- Group Policy management
- Domain joining
- Kerberos authentication
- LDAP
- NTLM

These services are compatible with locally deployed AD DS.

The benefit is that organizations can use domain-style services without deploying and managing additional domain controllers in the cloud.

---

# 28. Microsoft Entra Domain Services with Microsoft Entra Connect

Because Microsoft Entra ID can integrate with local AD DS, organizations can use Microsoft Entra Connect.

With Microsoft Entra Connect, users can use organizational credentials in both:

- On-premises AD DS
- Microsoft Entra Domain Services

Even if an organization does not have AD DS locally, it can use Microsoft Entra Domain Services as a cloud-only service.

This provides similar functionality to locally deployed AD DS without deploying any domain controller on-premises or in the cloud.

---

# 29. Example Scenario for Microsoft Entra Domain Services

An organization can:

- Create a Microsoft Entra tenant.
- Enable Microsoft Entra Domain Services.
- Deploy a virtual network between on-premises resources and the Microsoft Entra tenant.
- Enable Microsoft Entra Domain Services for that virtual network.

Then, on-premises users and services can use domain services from Microsoft Entra ID.

---

# 30. Benefits of Microsoft Entra Domain Services

Microsoft Entra Domain Services provides several benefits.

## No Need to Manage Domain Controllers

Administrators do not need to manage, update, patch, or monitor domain controllers.

## No Need to Manage AD Replication

Administrators do not need to deploy and manage Active Directory replication.

## No Need for Domain Admins or Enterprise Admins

There is no need to have Domain Admins or Enterprise Admins groups for domains managed by Microsoft Entra ID.

---

# 31. Limitations of Microsoft Entra Domain Services

The module also explained current limitations.

## Only Base Computer Active Directory Object Is Supported

Advanced computer object scenarios are limited.

## Schema Extension Is Not Supported

It is not possible to extend the schema for the Microsoft Entra Domain Services domain.

## OU Structure Is Flat

The OU structure is flat.

Nested OUs are not currently supported.

## Built-In Group Policy Object Exists

There is a built-in GPO for computer and user accounts.

## Built-In GPO Targeting Is Limited

It is not possible to target OUs with built-in GPOs.

You also cannot use:

- Windows Management Instrumentation filters
- Security-group filtering

---

# 32. Migrating Applications with Microsoft Entra Domain Services

Using Microsoft Entra Domain Services, organizations can migrate applications that use traditional protocols from on-premises infrastructure to the cloud.

Supported legacy protocols include:

- LDAP
- NTLM
- Kerberos

Organizations can also run applications such as:

- Microsoft SQL Server
- Microsoft SharePoint Server

on Azure virtual machines or in Azure IaaS without needing:

- Domain controllers in the cloud
- VPN connectivity back to local infrastructure

Microsoft Entra Domain Services can be enabled through the Azure portal.

It is charged per hour based on the size of the directory.

---

# 33. Knowledge Check Questions Covered

## Question 1

Which feature is unique to the Microsoft Entra ID P2 plan and not included in the P1 plan or the free version?

Correct answer:

```text
Microsoft Entra Identity Protection
```

Explanation:

Microsoft Entra ID Protection is a P2 feature that detects and manages identity-based risks.

## Question 2

When considering Microsoft Entra ID as a solution for managing internet-based applications, which authentication or authorization protocol does it primarily use?

Correct answer:

```text
OAuth
```

Explanation:

Microsoft Entra ID uses modern web protocols such as OAuth, OpenID Connect, SAML, and WS-Federation instead of traditional LDAP or Kerberos as its main cloud authentication and authorization model.

## Question 3

Which feature provided by Microsoft Entra ID P2 enhances security by managing privileges for administrators?

Correct answer:

```text
Microsoft Entra Privileged Identity Management
```

Explanation:

PIM manages privileged administrator roles and supports temporary or just-in-time administrative access.

## Question 4

A company needs to enhance security by enabling multi-factor authentication with their Microsoft Entra ID subscription. Which plan should they consider?

Correct answer:

```text
Microsoft Entra ID P1
```

Explanation:

Microsoft Entra ID P1 includes full multi-factor authentication features.

## Question 5

How does Microsoft Entra ID handle multi-tenancy compared to AD DS?

Correct answer:

```text
Microsoft Entra ID is inherently multi-tenant, allowing multiple directory instances across organizations.
```

Explanation:

Microsoft Entra ID is designed as a multi-tenant cloud directory service, while traditional AD DS is not designed in the same cloud multi-tenant model.

## Question 6

An enterprise is facing issues with inconsistent access patterns and potential security threats to its cloud applications. Which feature available in Microsoft Entra ID P1 can help address these concerns?

Correct answer:

```text
Advanced security reports and alerts
```

Explanation:

Advanced security reports and alerts help detect anomalies and inconsistent access patterns.

## Question 7

What is a significant difference between how organizational structures are managed in Microsoft Entra ID compared to AD DS?

Correct answer:

```text
Microsoft Entra ID uses a flat structure without OUs, while AD DS uses a hierarchical structure with OUs.
```

Explanation:

AD DS uses OUs and hierarchy, while Microsoft Entra ID uses a flat structure and relies more on groups, roles, and policies.

## Question 8

Which protocol is used by Microsoft Entra ID for authorization that differs from AD DS?

Correct answer:

```text
OAuth
```

Explanation:

Microsoft Entra ID uses OAuth for authorization, while AD DS traditionally uses Kerberos and LDAP-based directory access.

## Question 9

What is a key difference in the management structure between Microsoft Entra ID and AD DS?

Correct answer:

```text
Microsoft Entra ID uses a flat structure without OUs.
```

Explanation:

Microsoft Entra ID does not use traditional OUs like AD DS.

---

# 34. What Microsoft Entra Is

Microsoft Entra is a family of identity and network access products.

It helps organizations implement a Zero Trust security strategy.

The main idea of Zero Trust is:

```text
Never trust automatically. Always verify.
```

Microsoft Entra helps organizations:

- Verify identities
- Validate access conditions
- Check permissions
- Encrypt connection channels
- Monitor for compromise across the environment

Microsoft Entra also integrates with Security Copilot.

This helps investigate identity risks and troubleshoot access issues using AI.

---

# 35. Microsoft Entra Product Family

The Microsoft Entra product family spans:

- Identity
- Access
- Governance
- Security

It covers secure end-to-end access for:

- Employees
- Customers
- Partners
- Workloads
- AI agents

It works across cloud environments.

---

# 36. Microsoft Entra ID as the Foundational Product

Microsoft Entra ID is the foundational product of Microsoft Entra.

It is a cloud-based identity and access management service.

It provides:

- Authentication
- Policy enforcement
- Protection

For:

- Users
- Devices
- Applications
- Resources

Every new Microsoft Entra directory includes an initial domain name such as:

```text
contoso.onmicrosoft.com
```

Organizations can also add custom domain names.

If you use Microsoft 365, Azure, or Dynamics CRM Online, you are already using Microsoft Entra ID.

Every tenant is automatically a Microsoft Entra tenant.

---

# 37. Microsoft Entra Domain Services in the Microsoft Entra Product Family

Microsoft Entra Domain Services provides managed domain services such as:

- Group Policy
- LDAP
- Kerberos authentication
- NTLM authentication

It is designed for legacy applications in the cloud that cannot use modern authentication methods.

Example scenario:

An organization has services that need Kerberos authentication.

It can create a managed domain where Microsoft deploys and maintains the core service components.

---

# 38. Microsoft Entra Private Access

Microsoft Entra Private Access secures access to private applications and resources.

This includes:

- Corporate networks
- Internal applications
- Multicloud environments

It allows remote users to connect to internal resources from any device and network without using a traditional VPN.

Example:

An employee can securely access a corporate network printer while working from home or from a cafe.

---

# 39. Microsoft Entra Internet Access

Microsoft Entra Internet Access secures access to internet resources.

This includes:

- SaaS applications
- Microsoft 365 applications
- Microsoft 365 resources
- General internet resources

Example scenario:

An organization can enable web content filtering to regulate access to websites based on:

- Content categories
- Domain names

---

# 40. Microsoft Entra ID Governance

Microsoft Entra ID Governance simplifies identity and permissions management.

It automates:

- Access requests
- Access assignments
- Access reviews
- Identity lifecycle management

It helps protect critical assets by ensuring that users receive the right access when needed and lose that access when it is no longer needed.

Example:

Administrators can automatically assign user accounts, groups, and licenses to new employees.

When employees leave the company, those assignments can be removed automatically.

---

# 41. Microsoft Entra ID Protection

Microsoft Entra ID Protection detects and reports identity-based risks.

Administrators can investigate and automatically remediate risks.

It can work with tools such as risk-based Conditional Access policies.

Example:

An administrator can create Conditional Access policies that require MFA when the sign-in risk level is medium or high.

---

# 42. Microsoft Entra Verified ID

Microsoft Entra Verified ID is a credential verification service.

It is based on open decentralized identity standards.

It allows organizations to issue verifiable credentials.

A verifiable credential is a digital signature that proves the validity of information.

Users can store these credentials on their personal devices and present them when needed.

Example:

A college graduate can ask a university to issue a digital diploma to their decentralized identity.

The graduate can then present it to a potential employer.

The employer can independently verify:

- The issuer
- The issuance time
- The credential status

---

# 43. Microsoft Entra External ID

Microsoft Entra External ID allows external identities to safely access business resources and consumer applications.

It supports:

- Business partner collaboration
- Guest access
- Customer identity and access management
- Consumer-facing application identity

Example scenario:

An organization can set up self-service registration for customers.

Customers can sign in to a web application using:

- One-time passcodes
- Google accounts
- Facebook accounts

---

# 44. Microsoft Entra Workload ID

Microsoft Entra Workload ID is an identity and access management solution for workload identities.

Workload identities include:

- Applications
- Services
- Containers
- Automation jobs

These workloads need authentication and authorization policies.

Microsoft Entra Workload ID allows organizations to secure access to resources using:

- Adaptive policies
- Custom security attributes

Example:

GitHub Actions need a workload identity to access Azure subscriptions and automate software development workflows.

---

# 45. Microsoft Entra Agent ID

Microsoft Entra Agent ID is an identity and security framework for AI agents.

It extends Microsoft Entra capabilities to nonhuman AI identities.

It is designed for organizations that deploy:

- Assistive agents
- Autonomous agents
- User-like agents

Agent ID provides identity constructs to:

- Authenticate AI agents
- Authorize AI agents
- Govern AI agents
- Protect AI agents at enterprise scale

Example:

An organization deploys AI agents that access corporate data on behalf of users.

Agent ID gives each agent a governed identity, enforces least-privilege access, and maintains an audit trail of the agent’s actions.

---

# 46. Preparing the Environment for Microsoft Entra

Before deploying Microsoft Entra, organizations should configure infrastructure and processes according to security best practices and standards.

The referenced guidance areas were:

- Architecture
- Deployment plans
- Operations reference
- Operations guide
- Recommended security configurations

---

# 47. Microsoft Entra Licensing

Microsoft Entra features are licensed in multiple ways.

Licensing options include:

- Microsoft Entra ID Free
- Microsoft Entra ID P1
- Microsoft Entra ID P2
- Microsoft Entra Suite
- Microsoft Entra External ID
- Microsoft Entra Workload ID
- Microsoft Entra ID Governance
- Other standalone products

Microsoft Entra can also be part of broader Microsoft licenses such as:

- Microsoft 365
- Enterprise Mobility + Security

---

# 48. Managing and Developing with Microsoft Entra

Microsoft Entra can be managed and developed through several tools.

## Microsoft Entra Admin Center

The Microsoft Entra admin center is a web-based portal.

It allows administrators to configure and manage Microsoft Entra products from one interface.

## Microsoft Graph API

Microsoft Graph API can automate administrative tasks.

Examples include:

- License deployment
- User lifecycle management
- Identity management operations

## Microsoft Identity Platform

The Microsoft Identity Platform enables developers to build authentication experiences for:

- Web applications
- Desktop applications
- Mobile applications

It uses:

- Open-source libraries
- Standards-compliant authentication services

---

# 49. Final High-Level Architecture of Microsoft Entra

Microsoft Entra can be summarized as a family of products:

```text
Microsoft Entra
│
├── Microsoft Entra ID
│   └── Core cloud identity and access management
│
├── Microsoft Entra Domain Services
│   └── Managed domain services for legacy applications
│
├── Microsoft Entra Private Access
│   └── Secure access to private applications without VPN
│
├── Microsoft Entra Internet Access
│   └── Secure access to internet and SaaS resources
│
├── Microsoft Entra ID Governance
│   └── Identity lifecycle, access requests, assignments, and reviews
│
├── Microsoft Entra ID Protection
│   └── Risk detection and identity protection
│
├── Microsoft Entra Verified ID
│   └── Verifiable digital credentials
│
├── Microsoft Entra External ID
│   └── Customer, partner, and guest identity access
│
├── Microsoft Entra Workload ID
│   └── Identity for applications, services, and containers
│
└── Microsoft Entra Agent ID
    └── Identity and security framework for AI agents
```

---

# 50. Final Conceptual Summary

Microsoft Entra is Microsoft’s modern identity and access security platform.

Microsoft Entra ID is the core identity service inside Microsoft Entra.

AD DS is the traditional on-premises domain directory service.

Microsoft Entra ID is cloud-native and designed for modern web, SaaS, cloud, and identity-based access scenarios.

Microsoft Entra Domain Services bridges the gap for legacy applications that still need traditional domain protocols such as LDAP, Kerberos, and NTLM.

Microsoft Entra P1 adds advanced access, MFA, reporting, Conditional Access, and hybrid identity features.

Microsoft Entra P2 adds advanced identity protection and privileged identity management.

Microsoft Entra as a full product family expands beyond identity into:

- Zero Trust access
- Secure internet access
- Secure private access
- External identities
- Workload identities
- AI agent identities
- Governance
- Risk-based protection

The most important idea is that Microsoft Entra is not just “cloud Active Directory.”

It is a complete identity and access platform for modern environments, built around Zero Trust principles.