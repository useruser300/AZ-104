# Identity and Access Management Fundamental Concepts

## Purpose

This document explains the fundamental concepts of **Identity and Access Management (IAM)** and how IAM helps organizations secure resources effectively.

It focuses on the core idea that the right identity, whether a person, device, machine, application, service, script, or software component, should access the right resource at the right time with the right level of permission.

---

# What is Identity and Access Management (IAM)

**Identity and Access Management (IAM)** is the process of managing identities and controlling access to resources.

IAM answers two major questions:

```text
Who or what are you?
```

and:

```text
What are you allowed to access?
```

Before a user, device, machine, application, service, script, or software component can access a resource, it must first prove its identity.

After the identity is verified, the system decides whether access should be granted or denied.

---

# What IAM Does

IAM systems usually provide several core functions.

---

## Identity Management

**Identity Management** is the process of creating, storing, and managing identity information.

This includes information such as:

```text
Username
Email address
Password-related information
User role
Group membership
Permissions
Access level
Account status
```

The system or service responsible for managing identities is called an:

```text
Identity Provider (IdP)
```

An Identity Provider tracks and manages user identities, permissions, and access levels.

Examples include:

```text
Microsoft Entra ID
Google
GitHub
LinkedIn
Amazon
X
```

---

## Identity Federation

**Identity Federation** allows users who already have an identity somewhere else to access your system.

Instead of creating a completely separate username and password, the user can sign in using an existing identity.

Examples:

```text
Sign in with Microsoft
Sign in with Google
Sign in with GitHub
```

In an enterprise environment, this can also mean allowing users from a corporate network or external identity provider to access company applications.

The benefit is:

```text
Fewer accounts
Fewer passwords
Easier administration
Better centralized security
```

---

## Provisioning and Deprovisioning of Users

**Provisioning** means creating and configuring user accounts.

Example:

A new employee joins a company.

The company creates an account and defines:

```text
Which applications the user can access
Which groups the user belongs to
Which permissions the user has
Which resources are available to the user
```

**Deprovisioning** means removing, disabling, or revoking access when the user no longer needs it.

Example:

An employee leaves the company.

The company must disable the account or remove access so the former employee can no longer access company systems.

This is very important for security because old active accounts can become a serious risk.

---

## Authentication of Users

**Authentication** means confirming that a user, machine, or software component is really who or what it claims to be.

Example:

A user claims:

```text
I am Ali.
```

The system asks for proof, such as:

```text
Password
Fingerprint
Certificate
One-time passcode
Security key
```

If the proof is valid, authentication succeeds.

---

## Authorization of Users

**Authorization** means deciding what the authenticated user, machine, or software component is allowed to access.

Successful login does not mean full access to everything.

Example:

An HR employee may access employee records.

A Sales employee may not access HR records.

So the simple difference is:

```text
Authentication = Who are you?
Authorization = What are you allowed to do?
```

---

## Access Control

**Access Control** is the process of determining who or what has access to which resources.

It includes:

```text
User roles
Permissions
Policies
Authentication mechanisms
Authorization mechanisms
```

Access control regulates access to:

```text
Systems
Applications
Data
Networks
Resources
```

Examples:

```text
Only IT admins can access servers.
Only HR users can access employee records.
Only finance users can access accounting systems.
```

The goal is to make access controlled, intentional, and secure.

---

## Reports and Monitoring

IAM systems also provide reports and monitoring.

They can generate information about platform activity, such as:

```text
Sign-in time
Systems accessed
Authentication type
Failed login attempts
User behavior
Suspicious activity
```

Reports and monitoring help organizations:

```text
Ensure compliance
Assess security risks
Investigate incidents
Detect suspicious activity
Understand who accessed what and when
```

---

# Identity

## What is a Digital Identity

A **digital identity** is a collection of unique identifiers or attributes that represent an entity inside a system.

The entity can be:

```text
Person
Software component
Machine
Asset
Resource
```

A digital identity is not only for humans. Applications, services, scripts, containers, devices, and machines can also have identities.

---

## Examples of Identifiers

An identifier can be:

```text
Email address
Username and password
Bank account number
Government-issued ID
MAC address
IP address
```

Examples:

```text
ali@example.com
```

can identify a user.

```text
10.10.10.40
```

can identify a server or device.

```text
00:1A:2B:3C:4D:5E
```

can identify a network interface using a MAC address.

---

## Why Identities Are Used

Identities are used for:

```text
Authentication
Authorization
Communication
Transactions
Resource access
Security tracking
```

Without identity, the system cannot reliably know:

```text
Who is trying to access the system?
Is the entity trusted?
What permissions does the entity have?
What actions did the entity perform?
```

---

# Types of Identities

The article categorizes identities into three main types.

---

## Human Identities

**Human identities** represent people.

They include:

```text
Employees
Internal workers
Frontline workers
Customers
Consultants
Vendors
Partners
```

Examples:

```text
IT employee
HR employee
Customer using an application
External consultant
Business partner
```

---

## Workload Identities

**Workload identities** represent software workloads.

They are not human identities. They belong to applications, services, scripts, containers, or automation processes.

Examples:

```text
Application
Service
Script
Container
Automation job
```

Practical example:

A backend application needs to access a database.

Instead of using a human user account, the application should use its own workload identity.

This is very important in modern environments such as:

```text
Cloud
Containers
Microservices
Automation
CI/CD
```

---

## Device Identities

**Device identities** represent devices.

They include:

```text
Desktop computers
Mobile phones
IoT sensors
IoT-managed devices
```

Device identities are separate from human identities.

Examples:

A company laptop can have its own identity.

A mobile phone used to access company email can have its own identity.

An IoT sensor in a factory or hospital can have its own identity.

The key idea is that modern security does not only verify the user. It can also verify the device used by the user.

---

# Authentication

## What is Authentication

**Authentication** is the process of challenging a person, software component, or hardware device for credentials to verify its identity.

Authentication verifies:

```text
Are you really who or what you claim to be?
```

Authentication usually requires credentials such as:

```text
Username and password
Fingerprint
Certificate
One-time passcode
Face recognition
Security key
```

Authentication is sometimes shortened to:

```text
AuthN
```

---

## Multifactor Authentication (MFA)

**Multifactor Authentication (MFA)** is a security measure that requires users to provide more than one piece of evidence to verify their identity.

Instead of relying only on a password, MFA requires an additional factor.

The main factor categories are:

---

### Something You Know

Something the user knows.

Examples:

```text
Password
PIN
Security question
```

---

### Something You Have

Something the user has.

Examples:

```text
Badge
Mobile phone
Hardware token
Smart card
Security key
```

---

### Something You Are

Something the user is.

Examples:

```text
Fingerprint
Face
Iris
Voice
```

The benefit of MFA is that even if an attacker knows the password, they still need another factor to access the account.

---

## Single Sign-On (SSO)

**Single Sign-On (SSO)** allows users to authenticate once and then access multiple resources or applications that rely on the same identity.

Example:

A user signs in to Microsoft Entra ID.

Then the user can access:

```text
Outlook
Teams
SharePoint
Azure Portal
Company applications
```

without entering a password for each application separately.

Benefits of SSO:

```text
Better user experience
Fewer passwords
Fewer repeated sign-ins
Centralized identity security
Unified identity management
```

After authentication, the IAM system becomes the:

```text
Source of identity truth
```

This means other applications trust the IAM system to tell them who the user is.

---

# Authorization

## What is Authorization

**Authorization** validates that the user, machine, or software component is granted access to specific resources.

Authorization is sometimes shortened to:

```text
AuthZ
```

Authorization happens after successful authentication.

First, the system verifies the identity.

Then, the system decides the permissions.

Example:

Ali signs in successfully.

That does not mean Ali can access everything.

The system still needs to decide:

```text
Can Ali open this file?
Can Ali modify this resource?
Can Ali delete this record?
Can Ali access the admin panel?
```

---

# Authentication vs Authorization

Authentication and authorization may seem like one experience to the user, but they are two separate processes.

---

## Authentication

**Authentication** proves identity.

The main question is:

```text
Who are you?
```

Examples:

```text
Username and password
MFA
Certificate
Fingerprint
```

---

## Authorization

**Authorization** determines access.

The main question is:

```text
What are you allowed to access?
```

Examples:

```text
Read-only access
Admin access
Access to HR system
Access denied to finance system
```

---

# Authentication and Authorization Comparison

| Authentication | Authorization |
|---|---|
| Can be thought of as a gatekeeper that allows access only to entities that provide valid credentials. | Can be thought of as a guard that ensures only entities with proper clearance can enter certain areas. |
| Verifies whether a user, machine, or software is who or what they claim to be. | Determines whether a user, machine, or software is allowed to access a particular resource. |
| Challenges the user, machine, or software for verifiable credentials, such as passwords, biometric identifiers, or certificates. | Determines what level of access a user, machine, or software has. |
| Happens before authorization. | Happens after successful authentication. |
| Information is transferred in an ID token. | Information is transferred in an access token. |
| Often uses OpenID Connect (OIDC), which is built on OAuth 2.0, or SAML. | Often uses OAuth 2.0. |

---

# ID Token

An **ID token** is usually related to authentication.

It contains information that proves the identity of the user.

It tells the application:

```text
This user has been authenticated.
```

It can include information such as:

```text
User ID
Name
Email
Issuer
Authentication time
```

The main purpose of an ID token is not to grant access to resources. Its main purpose is to prove identity.

---

# Access Token

An **access token** is usually related to authorization.

It is used to access a specific resource.

It tells an API or resource:

```text
This entity has permission to access this resource or perform this action.
```

Example:

An application wants to read user data from an API.

The application sends an access token with the request.

The API checks the token and decides whether to allow or deny the request.

---

# OpenID Connect (OIDC)

**OpenID Connect (OIDC)** is commonly used for authentication.

It is built on top of:

```text
OAuth 2.0
```

Its main purpose is to prove the identity of the user to the application.

OIDC answers the question:

```text
Who is the user?
```

---

# OAuth 2.0

**OAuth 2.0** is commonly used for authorization.

Its main purpose is to allow an application or entity to access a specific resource on behalf of a user or according to defined permissions.

OAuth 2.0 answers the question:

```text
What access is allowed?
```

---

# SAML

**SAML** is also used in authentication and Single Sign-On scenarios, especially in enterprise environments and older enterprise applications.

It is commonly used to connect a central identity provider with external applications.

---

# Hotel Example

The article uses the hotel example to explain the difference between authentication and authorization.

---

## Hotel Authentication Example

Imagine you want to spend the night in a hotel.

You are the user.

The resources are:

```text
Hotel room
Exercise room
Hotel areas
```

First, you go to reception.

You show the receptionist:

```text
Identification card
Credit card
Reservation information
```

The receptionist matches your identity with the online reservation.

This represents:

```text
Authentication
```

because the hotel verifies that you are really the person who made the reservation.

After the verification, the receptionist gives you a:

```text
Keycard
```

---

## Hotel Authorization Example

After receiving the keycard, you go to your room.

When you swipe the keycard at the door, the sensor checks whether this keycard is allowed to open that door.

This represents:

```text
Authorization
```

because the question is no longer “Who are you?”

The question is:

```text
Are you allowed to open this door?
```

Your keycard may open:

```text
Your hotel room
Exercise room
```

But it cannot open:

```text
Other guest rooms
Staff-only areas
Storage rooms
```

If you try to open another guest’s room, access is denied.

---

# Roles and Permissions

The article explains that individual permissions can be collected into roles.

Instead of assigning every permission separately to every user, permissions can be grouped into a role.

Example from the hotel:

```text
Hotel Patron role
```

This role may allow access to:

```text
Assigned guest room
Exercise room
Public guest areas
```

Another example:

```text
Hotel Room Service role
```

This role may allow access to:

```text
All guest rooms
Laundry room
Supply closets
```

But only during a specific time:

```text
Between 11am and 4pm
```

This example is important because it shows that authorization can depend on:

```text
Role
Permission
Time condition
Resource type
Access scope
```

---

# Role-Based Access Control (RBAC) Concept

The article points to the idea of grouping permissions into roles.

This is closely related to:

```text
Role-Based Access Control (RBAC)
```

In RBAC, a user receives a role, and the role contains permissions.

Example:

```text
User: Ali
Role: IT Admin
Permissions:
- Access servers
- Manage users
- Read logs
```

Instead of assigning every permission directly to Ali, Ali is assigned the IT Admin role.

Benefits:

```text
Easier management
Better security
Fewer permission mistakes
Clearer access structure
Easier auditing
```

---

# Identity Provider

## What is an Identity Provider

An **Identity Provider (IdP)** is the system or service that creates, maintains, and manages identity information.

It also provides services such as:

```text
Authentication
Authorization
Auditing
```

It is the central place that knows:

```text
Who the users are
What their identities are
How they authenticate
Which access policies apply
What happened during sign-in
```

---

## Central Identity Provider

In modern authentication, every application does not manage usernames and passwords by itself.

Instead, applications rely on a central Identity Provider.

Example:

Instead of having separate passwords for:

```text
App 1
App 2
App 3
```

the organization uses a central provider such as:

```text
Microsoft Entra ID
```

Applications then trust that provider.

This makes identity management more secure, centralized, and easier to control.

---

# Benefits of a Central Identity Provider

A central Identity Provider helps organizations:

```text
Establish authentication policies
Establish authorization policies
Monitor user behavior
Identify suspicious activities
Reduce malicious attacks
Centralize identity management
Improve compliance
Simplify user access
Support SSO
Support MFA
```

Instead of spreading identities across many separate systems, identity becomes centralized, manageable, and monitorable.

---

# Microsoft Entra as an Identity Provider

**Microsoft Entra** is an example of a cloud-based Identity Provider.

It can be used to manage identities and access in modern environments, especially with Microsoft services, Azure, and enterprise applications.

Other examples of identity providers include:

```text
X
Google
Amazon
LinkedIn
GitHub
```

---

# Core Security Idea

The most important security idea in the article is that signing in successfully is not enough.

A secure system must also know:

```text
Who is the entity?
How was the entity verified?
Which device is being used?
Which resource is being requested?
Does the entity have permission?
What type of permission is allowed?
Is the activity normal or suspicious?
Should this event be logged?
```

That is why IAM is not only a login system.

IAM is a complete system for managing:

```text
Identity
Authentication
Authorization
Access control
Monitoring
Auditing
Compliance
Security risk assessment
```

---

# Practical Mental Model

A useful way to understand IAM is:

```text
Identity = Who or what is the entity?
Authentication = How do we prove the entity is real?
Authorization = What is the entity allowed to do?
Access Control = How do we enforce access rules?
Monitoring = How do we observe and review what happened?
Identity Provider = Who manages this process centrally?
```

---

# Most Important Takeaways

```text
IAM is the foundation for organizing and securing access to resources.
```

```text
Identity does not only mean a human user. It can also mean applications, services, scripts, containers, devices, and machines.
```

```text
Authentication means proving identity.
```

```text
Authorization means determining permissions after identity has been proven.
```

```text
MFA improves security because it requires more than one factor to verify identity.
```

```text
SSO improves the user experience because users sign in once and access multiple systems.
```

```text
An Identity Provider is the central system that manages identities, authentication, authorization, and auditing.
```

```text
Microsoft Entra is an example of a cloud-based Identity Provider.
```

```text
An ID token is related to proving user identity.
```

```text
An access token is related to accessing resources.
```

```text
OIDC is commonly used for authentication.
```

```text
OAuth 2.0 is commonly used for authorization.
```

```text
SAML is commonly used in SSO and enterprise integrations.
```

```text
Roles group multiple permissions to simplify access management.
```

```text
Reports and monitoring are essential parts of IAM because they help with compliance and security risk detection.
```

---

# Final Summary

**Identity and Access Management (IAM)** is the system that ensures the correct entity, whether it is a person, device, machine, application, service, script, or software component, can access the correct resource at the correct time with the correct level of permission.

The process starts with **Identity**, which defines the entity inside the system. Then **Authentication** proves that the entity is really who or what it claims to be. After that, **Authorization** determines what the entity is allowed to access. **Access Control** enforces these rules, and **Reports and Monitoring** help observe, audit, and secure the environment.

A central **Identity Provider**, such as **Microsoft Entra**, makes identity and access management more secure and organized because it provides one central place to manage users, policies, authentication, authorization, auditing, and suspicious activity detection.

The practical formula is:

```text
IAM = Identity + Authentication + Authorization + Access Control + Monitoring + Identity Provider
```

This is the foundation of modern security in companies, cloud environments, distributed systems, and enterprise applications.