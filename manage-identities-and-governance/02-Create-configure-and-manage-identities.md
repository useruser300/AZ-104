# Microsoft Entra ID User, Group, Device, Licensing, Custom Security Attributes, and Automatic Provisioning Concepts

## Introduction

Transitioning workloads to the cloud involves more than just moving servers, websites, and data.

Organizations must also think about how to secure those cloud resources by defining authorized users.

After defining authorized users, organizations must ensure that:

- Users only have access to the data they need.
- User authorization is limited to the services available to them.
- Users only perform operations they are authorized to perform.

Access to cloud-based workloads is controlled centrally in two main ways:

1. By providing a definitive identity for each user that they use for every service.
2. By ensuring employees and vendors have enough access to do their jobs.

Microsoft Entra ID is Microsoft’s cloud-based identity and access management service.

Microsoft Entra ID helps solve identity and access management challenges by providing end-to-end identity management, including:

- Single sign-on
- Multifactor authentication
- User management
- Group management
- License management
- Device registration
- Custom security attributes
- Automatic provisioning

## Learning Objectives

The main learning objectives covered were:

- Create, configure, and manage users.
- Create, configure, and manage groups.
- Manage licenses.
- Configure and manage device registration.
- Explore custom security attributes and automatic provisioning.

---

# Create, Configure, and Manage Users

Every user who needs access to resources needs a user account in Microsoft Entra ID.

A user account contains all the information needed to authenticate the user during the sign-on process.

After the user is authenticated, Microsoft Entra ID builds an access token.

The access token is used to:

- Authorize the user.
- Determine what resources the user can access.
- Determine what the user can do with those resources.

Administrators use the Microsoft Entra admin center to work with user objects.

Important administrative point:

- You can only work with a single directory at a time.
- You can use the **Directory + Subscription** panel to switch directories.
- The Microsoft Entra admin center also has a **Switch directory** button in the toolbar.

---

# View Users

To view Microsoft Entra users:

1. Select **Users** under **Identity**.
2. Open the **All Users** view.
3. Use the **User Type** column to identify members and guests.

Microsoft Entra ID commonly defines users in three main ways:

---

## Cloud Identities

Cloud identities are users that exist only in Microsoft Entra ID.

Examples include:

- Administrator accounts.
- Users that you manage directly yourself.

Their source can be:

- Microsoft Entra ID.
- External Microsoft Entra directory.

The external Microsoft Entra directory source is used when the user is defined in another Microsoft Entra instance but needs access to subscription resources controlled by the current directory.

Important behavior:

- When these accounts are removed from the primary directory, they are deleted.

---

## Directory-Synchronized Identities

Directory-synchronized identities are users that exist in an on-premises Active Directory.

A synchronization process brings these users into Microsoft Entra ID.

The recommended synchronization tool for most organizations is:

- Microsoft Entra Cloud Sync.

Microsoft Entra Cloud Sync:

- Uses a lightweight cloud-managed agent.
- Supports multiple disconnected forests.

Microsoft Entra Connect Sync is still available for complex scenarios, such as:

- Device synchronization.
- Groups with more than 50,000 members.

The source for these users is:

- Windows Server AD.

---

## Guest Users

Guest users are users that exist outside the organization.

Examples include:

- Accounts from other cloud providers.
- Microsoft accounts.
- External vendors.
- Contractors.

Their source is:

- Invited user.

Guest accounts are useful when external vendors or contractors need access to organizational resources.

When their help is no longer necessary, administrators can remove the account and all associated access.

---

# Create, Configure, and Manage Groups

A Microsoft Entra group helps organize users.

Groups make permission management easier because permissions can be assigned to a group instead of being assigned to each user individually.

Using groups allows the resource owner or Microsoft Entra directory owner to assign a set of access permissions to all members of the group.

Groups allow administrators to:

- Define a security boundary.
- Add users to grant access.
- Remove users to deny access.
- Manage access with less administrative effort.

Microsoft Entra ID supports the ability to define group membership based on rules.

Examples of rule-based membership conditions include:

- The department where a user works.
- The job title a user has.
- The location of the user.

---

# Types of Groups in Microsoft Entra ID

Microsoft Entra ID allows two main types of groups:

---

## Security Groups

Security groups are the most common type of group.

Security groups are used to manage access to shared resources.

Members of a security group can include:

- Users.
- Devices.
- Service principals.

Example:

An administrator can create a security group for a specific security policy.

By doing this, the administrator can give a set of permissions to all members at once instead of assigning permissions to each member individually.

This option requires a Microsoft Entra administrator.

---

## Microsoft 365 Groups

Microsoft 365 groups provide collaboration capabilities.

They give members access to:

- Shared mailbox.
- Calendar.
- Files.
- SharePoint site.
- Other collaboration resources.

Microsoft 365 groups also allow people outside the organization to access the group.

This option is available to:

- Users.
- Administrators.

---

# View Available Groups

Groups can be viewed from the **Groups** item under **Identity** in the Microsoft Entra admin center.

Important note:

- A new Microsoft Entra ID deployment has no groups defined by default.

---

# Membership Type

The second important characteristic of a group is the **Membership Type**.

Membership Type specifies how individual members are added to the group.

There are three main membership types:

---

## Assigned

Members are added and maintained manually.

---

## Dynamic User

Users are added and removed automatically based on rules.

These rules evaluate user attributes such as:

- Department.
- Job title.
- Location.

---

## Dynamic Device

Devices are added and removed automatically based on rules.

These rules evaluate device attributes.

Important note:

- Dynamic Device membership applies only to security groups.
- Microsoft 365 groups support dynamic users but not dynamic devices.

---

# Dynamic Groups

With dynamic membership, Microsoft Entra ID automatically adds or removes users or devices from a group based on rules defined by administrators.

When a member’s attributes change, all dynamic membership rules in the tenant are reevaluated.

Example:

If a user moves to a different department, Microsoft Entra ID reevaluates the rules and adds or removes the user from groups accordingly.

Dynamic membership requires:

- Microsoft Entra ID P1 license.

Or, for device-based rules:

- Intune for Education.

Example:

An administrator can create a rule that automatically adds all users whose **Department** attribute equals **Marketing** to a Marketing security group.

This keeps membership current without manual updates.

---

# Configure and Manage Device Registration

Because of the proliferation of devices of many shapes and sizes and the rise of bring-your-own-device scenarios, IT professionals must balance two goals:

1. Allow end users to be productive wherever, whenever, and on any device.
2. Protect the organization’s assets.

To protect organizational assets, IT staff first need to manage device identities.

IT staff can build on device identity with tools such as Microsoft Intune to ensure that security and compliance standards are met.

Microsoft Entra ID enables single sign-on to:

- Devices.
- Apps.
- Services.

The result is:

- Users get access to the organization’s assets they need.
- IT staff get the controls they need to secure the organization.

---

# Microsoft Entra Registered Devices

The goal of Microsoft Entra registered devices is to support BYOD and mobile device scenarios.

In these scenarios, a user can access Microsoft Entra ID-controlled organizational resources using a personal device.

## Microsoft Entra Registered Devices Description

| Microsoft Entra Registered | Description |
|---|---|
| Definition | Registered to Microsoft Entra ID without requiring organizational account to sign in to the device |
| Primary Audience | Applicable to Bring Your Own Device (BYOD) and mobile devices |
| Device Ownership | User or Organization |
| Operating Systems | Windows 10 or newer, macOS 10.15 or newer, iOS 15 or newer, Android, Linux Ubuntu 20.04/22.04/24.04 LTS, Red Hat Enterprise Linux 8/9 LTS |
| Device Sign-In Options | End-user local credentials, password, Windows Hello, PIN, biometrics |
| Device Management | Mobile Device Management, such as Microsoft Intune, and Mobile Application Management |
| Key Capabilities | SSO to cloud resources, Conditional Access when enrolled in Intune, Conditional Access through App Protection Policy |

Microsoft Entra registered devices are signed in to using a local account.

Example:

- A Microsoft account on a Windows 10 or newer device.

Additionally, the device has a Microsoft Entra account attached for access to organizational resources.

Access to resources in the organization can be further limited based on:

- The Microsoft Entra account.
- Conditional Access policies.
- Device identity.

Administrators can secure and further control Microsoft Entra registered devices using Mobile Device Management tools such as Microsoft Intune.

MDM provides a way to enforce organization-required configurations, such as:

- Requiring storage to be encrypted.
- Requiring password complexity.
- Keeping security software updated.

Microsoft Entra ID registration can be done:

- When accessing a work application for the first time.
- Manually using the Windows 10 or Windows 11 Settings menu.

---

# Scenarios for Registered Devices

## Scenario 1: Home PC Access

A user in the organization wants to access tools for:

- Email.
- Reporting time-off.
- Benefits enrollment.

The user wants to access these tools from a home PC.

The organization protects these tools with a Conditional Access policy that requires access from an Intune-compliant device.

The user adds the organization account and registers the home PC with Microsoft Entra ID.

The required Intune policies are enforced.

The user gets access to the required resources.

---

## Scenario 2: Rooted Android Phone

Another user wants to access organizational email on a personal Android phone infected by a rootkit.

The company requires a compliant device.

The company has created an Intune compliance policy to block rooted devices.

The employee is prevented from accessing organizational resources on that device.

---

# Microsoft Entra Joined Devices

Microsoft Entra joined is intended for organizations that want to be:

- Cloud-first.
- Cloud-only.

Any organization can deploy Microsoft Entra joined devices regardless of size or industry.

Microsoft Entra joined enables access to both:

- Cloud apps and resources.
- On-premises apps and resources.

## Microsoft Entra Joined Devices Description

| Microsoft Entra Joined | Description |
|---|---|
| Definition | Joined only to Microsoft Entra ID requiring organizational account to sign in to the device |
| Primary Audience | Suitable for both cloud-only and hybrid organizations |
| Device Ownership | Organization |
| Operating Systems | All Windows 10 and Windows 11 devices except Home editions; Windows Server 2019 and newer VMs in Azure, Server Core not supported; macOS 13 or newer preview |
| Device Management | Mobile Device Management, such as Microsoft Intune |
| Key Capabilities | SSO to both cloud and on-premises resources, Conditional Access, Self-Service Password Reset, Windows Hello PIN reset |

Microsoft Entra joined devices are signed in to using an organizational Microsoft Entra account.

Access to resources in the organization can be further limited based on:

- The Microsoft Entra account.
- Conditional Access policies.
- Device identity.

Administrators can secure and further control Microsoft Entra joined devices using:

- Microsoft Intune.
- Microsoft Endpoint Configuration Manager.
- Co-management scenarios.

These tools provide a way to enforce organization-required configurations, such as:

- Requiring storage to be encrypted.
- Password complexity.
- Software installations.
- Software updates.

Administrators can make organization applications available to Microsoft Entra joined devices using Configuration Manager.

Microsoft Entra joined can be accomplished using self-service options such as:

- Out of Box Experience (OOBE).
- Bulk enrollment.
- Windows Autopilot.

Microsoft Entra joined devices can still maintain single sign-on access to on-premises resources when they are on the organization’s network.

Microsoft Entra joined devices authenticate to on-premises servers such as:

- File servers.
- Print servers.
- Other application servers.

---

# Scenarios for Joined Devices

Although Microsoft Entra joined is primarily intended for organizations that do not have an on-premises Windows Server Active Directory infrastructure, it can also be used in other scenarios.

Use Microsoft Entra joined if:

- You want to transition to cloud-based infrastructure using Microsoft Entra ID and MDM such as Intune.
- You cannot use an on-premises domain join.
- You need to get mobile devices such as tablets and phones under control.
- Users primarily need access to Microsoft 365 or other SaaS apps integrated with Microsoft Entra ID.
- You want to manage a group of users in Microsoft Entra ID instead of Active Directory.
- You want to manage seasonal workers, contractors, or students in Microsoft Entra ID.
- You want to provide joining capabilities to workers in remote branch offices with limited on-premises infrastructure.

Microsoft Entra joined devices can be configured for:

- Windows 10.
- Windows 11.

Except:

- Home editions.

The goal of Microsoft Entra joined devices is to simplify:

- Windows deployments of work-owned devices.
- Access to organizational apps and resources from any Windows device.
- Cloud-based management of work-owned devices.
- Users signing in to their devices with Microsoft Entra ID or synced Active Directory work or school accounts.

Microsoft Entra joined can be deployed by using many different methods.

---

# Hybrid Microsoft Entra Joined Devices

For more than a decade, many organizations have used domain join to on-premises Active Directory.

This enabled:

- IT departments to manage work-owned devices from a central location.
- Users to sign in to their devices with Active Directory work or school accounts.

Organizations with an on-premises footprint typically rely on imaging methods to configure devices.

They often use:

- Configuration Manager.
- Group Policy (GP).

If the environment has an on-premises Active Directory footprint and the organization also wants to benefit from Microsoft Entra ID capabilities, it can implement Hybrid Microsoft Entra joined devices.

Hybrid Microsoft Entra joined devices are:

- Joined to on-premises Active Directory.
- Registered with the Microsoft Entra directory.

## Hybrid Microsoft Entra Joined Devices Description

| Hybrid Microsoft Entra Joined | Description |
|---|---|
| Definition | Joined to on-premises AD and Microsoft Entra ID requiring organizational account to sign in to the device |
| Primary Audience | Suitable for hybrid organizations with existing on-premises AD infrastructure |
| Device Ownership | Organization |
| Operating Systems | Windows 10, Windows 11 except Home editions, Windows Server 2016, 2019, and 2022 |
| Device Sign-In Options | Password or Windows Hello for Business |
| Device Management | Group Policy, Configuration Manager standalone, or co-management with Microsoft Intune |
| Key Capabilities | SSO to both cloud and on-premises resources, Conditional Access, Self-Service Password Reset, Windows Hello PIN reset |

---

# Scenarios for Hybrid Joined

Use Microsoft Entra hybrid joined devices if:

- You have Win32 apps deployed to these devices that rely on Active Directory machine authentication.
- You want to continue to use Group Policy to manage device configuration.
- You want to continue to use existing imaging solutions to deploy and configure devices.

---

# Device Writeback No Longer Supported

Device writeback is no longer supported.

Device writeback is no longer a recommended approach for hybrid identity scenarios.

It has been replaced by:

- Cloud Kerberos Trust.

Cloud Kerberos Trust allows Microsoft Entra joined and hybrid joined devices to authenticate to on-premises resources without requiring device objects to be written back to on-premises Active Directory.

For organizations planning new hybrid deployments, Cloud Kerberos Trust should be used to enable:

- On-premises SSO.
- Windows Hello for Business.
- Hybrid environment authentication.

---

# Manage Licenses

Microsoft paid cloud services require licenses.

Examples include:

- Microsoft 365.
- Enterprise Mobility + Security.
- Dynamics 365.
- Other similar Microsoft cloud products.

These licenses are assigned to each user who needs access to these services.

Administrators manage licenses using:

- Microsoft 365 admin center.
- PowerShell.
- Microsoft Graph API.

Microsoft Entra ID is the underlying infrastructure that supports identity management for all Microsoft cloud services.

Microsoft Entra ID stores information about license assignment states for users.

---

# Why Individual License Assignment Is Difficult

Without group-based licensing, assigning licenses at the individual user level makes large-scale management difficult.

Example:

To add or remove user licenses based on organizational changes, such as users joining or leaving the organization or a department, an administrator often must write a complex PowerShell script.

That script makes individual calls to the cloud service.

---

# Group-Based Licensing in Microsoft Entra ID

Group-based licensing in Microsoft Entra ID allows administrators to assign product licenses to groups instead of assigning them individually to each user.

When a license is assigned to a group:

- All current members inherit the license automatically.
- New members receive the license automatically.
- Members who leave the group lose the inherited license automatically.

This approach simplifies license management and eliminates the need for custom automation scripts.

---

# How Group-Based Licensing Works

Microsoft Entra ID stores the license assignment intent on the group.

For each member of the group, Microsoft Entra ID attempts to apply the assigned license.

If the assignment succeeds:

- The user receives the license as an inherited assignment.

If the assignment fails:

- The user enters a licensing error state.
- The error is recorded on the user object.
- The assignment intent remains stored and can be retried later.

---

# License Requirements

You must have one of the following licenses to use group-based licensing:

- Paid or trial subscription for Microsoft Entra ID Premium P1 and greater.
- Paid or trial edition Office 365 Enterprise E3 or greater.

---

# Required Number of Licenses

For any groups assigned a license, you must also have a license for each unique member.

You do not have to assign each member of the group a license manually.

However, you must have at least enough licenses to include all members.

Example:

If you have 1,000 unique members who are part of licensed groups in your tenant, you must have at least 1,000 licenses to meet the licensing agreement.

---

# Features of Group-Based Licensing

The main features of group-based licensing are:

- Licenses can be assigned to any security group in Microsoft Entra ID.
- Security groups can be synced from on-premises by using Microsoft Entra Cloud Sync.
- Microsoft Entra Cloud Sync is recommended for most organizations.
- Security groups can also be synced from on-premises by using Microsoft Entra Connect Sync.
- Security groups can be created directly in Microsoft Entra ID.
- Security groups created directly in Microsoft Entra ID are also called cloud-only groups.
- Security groups can be created automatically by using the Microsoft Entra dynamic group feature.
- When a product license is assigned to a group, the administrator can disable one or more service plans in the product.
- Disabling service plans is typically done when the organization is not yet ready to use a service included in a product.
- Example: An administrator might assign Microsoft 365 to a department but temporarily disable the Viva Engage service.
- All Microsoft cloud services that require user-level licensing are supported.
- Supported services include all Microsoft 365 products, Enterprise Mobility + Security, and Dynamics 365.
- Group-based licensing is currently available only through the Microsoft 365 admin center.
- Microsoft Entra ID automatically manages license modifications that result from group membership changes.
- License modifications are typically effective within minutes of a membership change.
- A user can be a member of multiple groups with license policies specified.
- A user can also have some licenses that were directly assigned outside of any groups.
- The resulting user state is a combination of all assigned product and service licenses.
- If a user is assigned the same license from multiple sources, the license is consumed only once.
- In some cases, licenses cannot be assigned to a user.
- One possible reason is that there are not enough available licenses in the tenant.
- Another possible reason is that conflicting services are assigned at the same time.
- Administrators have access to information about users for whom Microsoft Entra ID could not fully process group licenses.
- Administrators can take corrective action based on that information.
- Some Microsoft services are not available in all locations.
- Before assigning a license to a user, the administrator should specify Usage Location in the User Profile.
- For group license assignment, users without a usage location inherit the location of the directory.
- If users exist in multiple locations, Usage Location should always be set as part of user creation.
- Usage Location helps ensure the result of license assignment is always correct.
- Usage Location helps ensure users do not receive services in locations where those services are not allowed.

---

# Common License Assignment Errors

## 1. Not Enough Licenses (`CountViolation`)

### Cause

The number of available licenses is insufficient for all users in the group.

### Resolution

- Purchase additional licenses.
- Remove unused licenses from other users or groups.
- Reduce the size of the licensed group.

---

## 2. Conflicting Service Plans (`MutuallyExclusiveViolation`)

### Cause

Two licenses include service plans that cannot coexist on the same user.

### Example

- Office 365 E1 assigned directly.
- Office 365 E3 assigned through a group.

Conflicts may occur between:

- Exchange Online Plan 1 and Plan 2.
- SharePoint Online Plan 1 and Plan 2.

### Resolution

- Remove the old license.
- Disable conflicting service plans.
- Keep only the required product license.

---

## 3. Dependency Violations (`DependencyViolation`)

### Cause

A service plan being removed is required by another assigned service.

### Resolution

- Ensure the prerequisite plan remains assigned.
- Remove dependent services before removing the prerequisite license.

---

## 4. Usage Location Not Allowed (`ProhibitedInUsageLocationViolation`)

### Cause

The user's Usage Location is missing or unsupported.

### Resolution

Set the correct Usage Location for the user before assigning licenses.

---

## 5. Duplicate Proxy Addresses

### Cause

Two users have the same proxy address.

### Resolution

Correct duplicate values in the `proxyAddresses` attribute.

---

## 6. LicenseAssignmentAttributeConcurrencyException

### Cause

The same license is being assigned simultaneously from multiple groups.

### Resolution

No action is required.

Microsoft Entra ID automatically retries processing.

---

# Multiple Product Licenses Assigned to a Group

A single group can be assigned multiple licenses, such as:

- Microsoft 365 E3.
- Enterprise Mobility + Security.

Microsoft Entra ID attempts to assign all products to each group member.

If one product fails due to licensing or business logic issues, the assignment of other products in the same operation may also fail.

---

# Add-On Licenses and Prerequisites

Some Microsoft products are add-ons and require prerequisite service plans.

### Example

Microsoft Workplace Analytics requires:

- Exchange Online Plan 1 or Plan 2.

### Key Rule

The prerequisite and the add-on must be assigned together so the service functions correctly.

---

# Reprocessing License Assignments

After resolving licensing issues, administrators can manually trigger reprocessing.

---

## Group Reprocessing

Group reprocessing reruns license processing for all members of a group.

---

## User Reprocessing

User reprocessing reruns license processing for a specific user.

This is useful after fixing:

- License shortages.
- Usage location issues.
- Duplicate proxy addresses.
- Service conflicts.

---

# Migration from Direct Licensing to Group-Based Licensing

Organizations often start with direct license assignments using:

- PowerShell.
- Manual processes.

The recommended migration approach is:

1. Keep existing direct assignments in place.
2. Create licensing groups.
3. Assign the same licenses to those groups.
4. Confirm users have both direct and inherited licenses.
5. Verify no errors exist.
6. Gradually remove direct assignments.

### Important Note

When a user has the same license assigned both directly and through a group, only one license is consumed.

---

# Changing License Plans Example: E1 to E3

Microsoft Entra ID processes license removals and new assignments simultaneously.

This ensures:

- No service interruption.
- No temporary loss of access.
- No data loss.

---

# Requirements Before Updating License Assignments

Before moving users or groups to a new license plan, verify that:

- Users currently have the expected license.
- Enough new licenses are available.
- No conflicting licenses exist.
- Dependencies are satisfied.
- Group membership changes are synchronized if groups are managed on-premises.

---

# Direct vs Inherited License Assignments

| Assignment Type | Description |
|---|---|
| Direct | Assigned explicitly to the user |
| Inherited | Assigned through group membership |

---

# Licensed Group Deletion Behavior

A group cannot be deleted until all assigned licenses are removed.

When licenses are removed during group deletion:

- Microsoft Entra ID attempts to remove inherited licenses.
- If a dependent add-on license exists, the inherited base license may be converted to a direct assignment to preserve service continuity.

---

# Key PowerShell Error Codes

| Error Code | Meaning |
|---|---|
| CountViolation | Insufficient licenses |
| MutuallyExclusiveViolation | Conflicting service plans |
| DependencyViolation | Missing prerequisite dependency |
| ProhibitedInUsageLocationViolation | Invalid or missing Usage Location |

---

# Key Benefits of Group-Based Licensing

Group-based licensing provides:

- Centralized license management.
- Automatic assignment and removal.
- Reduced administrative effort.
- Fewer custom scripts.
- Better consistency.
- Easier auditing and troubleshooting.

---

# Core Concept to Remember

Group-based licensing separates **license intent** from **license application**.

- The group stores the intent.
- Microsoft Entra ID applies the license to each member.
- Errors are tracked per user.
- Reprocessing allows automatic retry after issues are resolved.

Example of the concept:

```text
Group = stores license intent
User = receives license application
Error = tracked per user
Reprocessing = retries after issue is fixed
```

---

# Create Custom Security Attributes

Custom security attributes in Microsoft Entra ID are business-specific attributes.

They are key-value pairs that administrators can define and assign to Microsoft Entra objects.

Custom security attributes can be used to:

- Store information.
- Categorize objects.
- Enforce fine-grained access control over specific Azure resources.

Custom security attributes can be created using data types such as:

- String.
- Integer.
- Boolean.

---

# What Are Custom Security Attributes?

Custom Security Attributes in Microsoft Entra ID are custom properties, or additional fields, that an organization creates and assigns to:

- Users.
- Enterprise Applications.
- Service Principals.

These attributes are used to store business-specific information.

They can later be used for:

- Classification.
- Access control.
- Governance.
- Filtering.

---

# The Basic Idea

Microsoft Entra ID already includes built-in attributes such as:

- Name.
- Department.
- Job Title.
- Email Address.

However, organizations often need to store additional information that is not part of the default schema.

Examples include:

- HourlySalary.
- Project.
- CostCenter.
- SecurityLevel.

Custom Security Attributes allow administrators to create these fields.

---

# Simple Example

Suppose you have a user named Ali.

Built-in attributes:

- Name = Ali.
- Department = IT.

Custom security attributes:

- HourlySalary = 35.
- Project = ERP.
- SecurityLevel = Confidential.

---

# Why Are They Called Security Attributes?

They are called security attributes because their values can be used in access control decisions.

Example:

If a user has:

- Project = Alpha.

Then the user can be granted access only to resources that also have:

- Project = Alpha.

---

# Why Use Custom Security Attributes?

Organizations use custom security attributes to:

- Extend user profiles, such as adding Hourly Salary to all employees.
- Ensure only administrators can see the Hourly Salary attribute in employee profiles.
- Categorize hundreds or thousands of applications to easily create a filterable inventory for auditing.
- Grant users access to Azure Storage blobs belonging to a project.

---

# What Can I Do with Custom Security Attributes?

With custom security attributes, administrators can:

- Define business-specific information for the tenant.
- Add custom security attributes to Microsoft Entra users.
- Add custom security attributes to enterprise applications.
- Add custom security attributes to service principals.
- Manage Microsoft Entra objects using custom security attributes with queries and filters.
- Provide attribute governance so attributes determine who can get access.

Custom security attributes are not supported in:

- Microsoft Entra Domain Services.
- SAML token claims.
- JSON Web Token JWT claims.

---

# Main Use Cases

## 1. Store Additional Business Information

Examples:

- HourlySalary.
- ProjectCode.
- CostCenter.

---

## 2. Classify Users and Applications

Examples:

- Production.
- Test.
- Finance.
- Confidential.

---

## 3. Fine-Grained Access Control (ABAC)

Attribute values can be used in authorization conditions.

This allows access decisions to be based on attributes.

---

## 4. Search and Filter

Example:

- Show all users where Project = ERP.

---

# Supported Data Types

Custom Security Attributes support:

- String.
- Integer.
- Boolean.

---

# Single Value vs Multi Value

## Single Value

Only one value is allowed.

Example:

- Department = Finance.

---

## Multi Value

Multiple values are allowed.

Example:

- Skills = Linux, Azure, Terraform.

---

# Free-Form vs Predefined Values

## Free-Form

Administrators can enter any value.

---

## Predefined Values

Only approved values are allowed.

Example:

- Public.
- Internal.
- Confidential.
- Secret.

---

# Where Can They Be Assigned?

Custom Security Attributes can be assigned to:

- Users.
- Enterprise Applications.
- Service Principals.

They can also be assigned to directory-synchronized users from an on-premises Active Directory.

---

# Practical Example

An organization wants to classify applications:

- CRM = Confidential.
- HR = Secret.
- Website = Public.

This classification can then be used in access control policies.

---

# Controlling Who Can View or Edit Attributes

Administrators can define who is allowed to:

- Read attribute values.
- Modify attribute values.
- Assign attribute values.

Example:

Only HR administrators can view the `HourlySalary` attribute.

---

# Scope

Custom Security Attributes are available tenant-wide.

This means they can be used across the entire organization.

---

# Integration with On-Premises Active Directory

Custom Security Attributes can be assigned to users synchronized from Active Directory Domain Services.

---

# Limitations

Custom Security Attributes are not supported in:

- SAML token claims.
- JWT claims.
- Microsoft Entra Domain Services.

---

# Features of Custom Security Attributes

Custom security attributes:

- Are available tenant-wide.
- Include a description.
- Support different data types: Boolean, Integer, String.
- Support single value or multiple values.
- Support user-defined free-form values or predefined values.
- Can be assigned to directory-synchronized users from an on-premises Active Directory.

---

# Simple Analogy

Think of Microsoft Entra ID as an Excel spreadsheet.

Built-in columns:

- Name.
- Department.
- Email.

Custom columns you add:

- HourlySalary.
- Project.
- SecurityLevel.

These additional columns are Custom Security Attributes.

---

# Summary of Custom Security Attributes

Custom Security Attributes are organization-defined fields in Microsoft Entra ID.

They allow organizations to store additional information about users and applications.

They can be used for:

- Classification.
- Governance.
- Filtering.
- Fine-grained access control.

---

# What Is Automatic User Creation?

Automatic User Creation, also called **Automatic Provisioning**, is the process of creating, updating, and deleting user accounts automatically across systems.

In Microsoft environments, Microsoft Entra ID can automatically provision users and groups to other applications and systems.

---

# The Basic Idea of Automatic Provisioning

Instead of manually creating accounts in every system:

1. HR adds a new employee.
2. The employee record is synchronized to Microsoft Entra ID.
3. Microsoft Entra automatically creates accounts in target applications.
4. If the employee changes departments, attributes are updated automatically.
5. If the employee leaves the company, accounts are disabled or removed automatically.

---

# Real-World Example

Suppose HR creates a new employee:

- Name: Ali
- Department: IT.
- Job Title: System Administrator.

Automatic provisioning can create accounts in:

- Microsoft 365.
- Salesforce.
- ServiceNow.
- Slack.

No manual account creation is required.

---

# Main Components

## 1. HCM System

HCM means Human Capital Management system.

Examples include:

- Workday.
- SAP SuccessFactors.

The HCM system is considered the source of truth for employee data.

---

## 2. Microsoft Entra ID

Microsoft Entra ID acts as the central identity repository.

---

## 3. Microsoft Entra Provisioning Service

The Microsoft Entra Provisioning Service reads users from the source system and provisions them to target systems.

---

## 4. Target System

The target system is any application or system that receives users and groups.

Examples include:

- Salesforce.
- ServiceNow.
- Slack.
- Google Workspace.

---

# What Is SCIM?

SCIM stands for **System for Cross-domain Identity Management**.

SCIM is an open standard protocol used to exchange identity information between identity domains and IT systems.

---

# What SCIM Provides

SCIM defines:

- A standard user schema.
- A standard group schema.
- REST APIs for:
  - Create user.
  - Update user.
  - Disable user.
  - Delete user.
  - Manage group membership.

---

# Why SCIM Is Important

Without SCIM, every application would need a custom integration.

With SCIM, Microsoft Entra can provision users to any application that supports SCIM.

---

# Provisioning Lifecycle

## Joiner

A new employee joins the organization.

Result:

- Account created automatically.

---

## Mover

An employee changes role or department.

Result:

- Attributes are updated automatically.
- Group memberships are updated automatically.

---

## Leaver

An employee leaves the organization.

Result:

- Account is disabled or removed automatically.

---

# Example Workflow

1. HR creates Ali in Workday.
2. Workday syncs Ali to Entra ID.
3. Entra assigns groups and licenses.
4. The Provisioning Service creates Ali in Salesforce and ServiceNow.
5. Ali leaves the company.
6. HR marks Ali as terminated.
7. Entra disables all related accounts automatically.

---

# Benefits of Automatic User Creation

Automatic User Creation provides:

- Elimination of manual account creation.
- Reduced errors.
- Faster onboarding.
- Improved security.
- Immediate deprovisioning.
- Better compliance.

---

# API-Driven Inbound Provisioning

Not all HR systems support SCIM.

Microsoft Entra supports API-based inbound provisioning.

In this model, any script or automation tool can send workforce data to the provisioning API.

This allows integration with virtually any HR system.

---

# Source of Truth Concept

The authoritative source for identity data is usually:

- Workday.
- SAP SuccessFactors.
- Another HR system.

Changes should originate in the source of truth.

They should not normally be made directly in Entra.

---

# Practical Example of Automatic Updates

If HR changes:

- Department = Finance → IT.

Then Entra automatically updates:

- Department attribute.
- Group memberships.
- Application roles.
- Access rights.

---

# Summary of Automatic User Creation

Automatic User Creation is the automated identity lifecycle process where Microsoft Entra ID receives user data from HR or another source system.

Microsoft Entra ID then automatically creates, updates, and removes user accounts in connected applications using:

- SCIM.
- APIs.

This supports the full identity lifecycle:

- Joiner.
- Mover.
- Leaver.

---

# Final Core Summary

WE covered the most important Microsoft Entra ID concepts related to identity, access, users, groups, devices, licenses, custom attributes, and provisioning.

The most important connected ideas are:

- Users represent identities that authenticate and receive access tokens.
- Microsoft Entra ID uses access tokens to authorize access to resources.
- Users can be cloud identities, directory-synchronized identities, or guest users.
- Groups organize users and simplify permission management.
- Security groups are used mainly for access control.
- Microsoft 365 groups are used mainly for collaboration.
- Dynamic groups automate membership based on user or device attributes.
- Device registration controls how personal, corporate, cloud-only, hybrid, and on-premises-connected devices access organizational resources.
- Microsoft Entra registered devices are mainly for BYOD and mobile scenarios.
- Microsoft Entra joined devices are mainly for cloud-first or cloud-only organization-owned devices.
- Hybrid Microsoft Entra joined devices are for organizations that still use on-premises Active Directory but also want Microsoft Entra ID capabilities.
- Device writeback is no longer supported and is replaced by Cloud Kerberos Trust.
- Group-based licensing automates license assignment and removal through group membership.
- Group-based licensing separates license intent from license application.
- Licensing errors are tracked per user and can be corrected through reprocessing.
- Custom Security Attributes extend Microsoft Entra ID with organization-specific fields.
- Custom Security Attributes support classification, filtering, governance, and fine-grained access control.
- Automatic Provisioning automates account creation, update, and removal across systems.
- SCIM provides a standard way for Microsoft Entra ID to provision users and groups into supported applications.
- HR systems such as Workday or SAP SuccessFactors often act as the source of truth.
- The full identity lifecycle is best understood as Joiner, Mover, and Leaver.
