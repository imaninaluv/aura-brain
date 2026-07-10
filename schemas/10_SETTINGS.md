# Settings

Version: 1.0
Status: Locked
Last Updated: 2026-07-09

---

# Overview

The Settings section allows users to manage their Aura AI account, application preferences, and connected services.

Its purpose is to provide a single location where users can review, update, and maintain their account configuration without affecting their existing content.

Settings are intended for long-term account configuration rather than day-to-day content creation.

---

# Objectives

The Settings section has five primary objectives:

- Manage account information.
- Configure application preferences.
- Manage the connected Threads account.
- View subscription and usage information.
- Access account and application management options.

Changes made within Settings should take effect across the entire application where applicable.

---

# Design Principles

The Settings experience follows these principles:

### Simplicity

Settings should remain organised and easy to navigate.

Related options should be grouped together to reduce complexity.

---

### Consistency

Account preferences should behave consistently throughout the application.

Changes made within Settings should automatically become the new default configuration where appropriate.

---

### User Control

Users should have full control over their account preferences.

Aura AI should never modify user settings without explicit user action.

---

# Settings Categories

The Settings section is organised into the following categories:

```
Account

↓

Preferences

↓

Subscription

↓

Application
```

Each category contains settings related to a specific aspect of the user's Aura AI experience.


---

# Account

The Account section contains information related to the user's Aura AI account and connected Threads account.

This section allows users to review their account information and manage their connected account.

---

# Aura AI Account

The following information should be displayed:

- Display Name
- Email Address
- Account Creation Date

These fields are for reference only unless otherwise specified.

---

# Connected Threads Account

The connected Threads account should display:

- Profile Picture
- Display Name
- Username
- Connection Status

This information is synchronised from the connected Threads account.

---

# Account Management

Users may perform the following actions:

- Connect Threads Account
- Reconnect Threads Account
- Disconnect Threads Account

Changes to the connected account should take effect throughout the application after successful synchronisation.

---

# Connection Status

The application should support the following connection states:

### Connected

The Threads account is successfully connected and synchronised.

---

### Disconnected

No Threads account is currently connected.

Features requiring a connected account should remain unavailable until a connection has been established.

---

### Synchronising

Account information is currently being synchronised.

The user should wait until synchronisation has completed before performing additional account actions.

---

### Connection Error

The application was unable to connect or synchronise the Threads account.

The user should be informed of the failure and given the option to retry the connection.



---

# Preferences

The Preferences section allows users to customise how Aura AI behaves throughout the application.

Changes made within this section become the default preferences for future interactions unless modified again.

---

# Language Preference

Users may change their default language preference.

This language is used as the default language for:

- Content generation.
- Reply generation.
- Analytics explanations.
- Application text where applicable.

Users may still override the language for individual content generation when supported.

---

# Primary Content Category

Users may update their primary content category at any time.

Examples include:

- Education
- Marketing
- Sales
- Business
- Technology
- Food
- Sports
- Lifestyle
- Beauty
- Gaming
- Finance
- Entertainment
- Travel
- Productivity
- Other

This preference helps personalise the overall Aura AI experience.

---

# Preference Synchronisation

Changes made within Preferences should be applied immediately after being saved.

Updated preferences become available across all applicable features without requiring the user to complete onboarding again.

---

# Default Behaviour

If a preference has not been explicitly configured, Aura AI should use the values selected during onboarding.

Preferences always take precedence over the initial onboarding configuration once they have been updated.



---

# Subscription

The Subscription section provides users with information about their current Aura AI plan and monthly usage.

This section allows users to understand their available resources and manage their subscription.

---

# Current Plan

The active subscription plan should be displayed.

Examples include:

- Standard
- Premium
- Business

The current plan determines the user's available monthly usage and feature access.

---

# Monthly Usage

Users should be able to view their current monthly usage.

Examples include:

- Tokens Used
- Tokens Remaining
- Monthly Reset Date

Usage information should update automatically as the user consumes available resources.

---

# Plan Management

Users may perform the following actions:

- View Current Plan
- Upgrade Plan
- Downgrade Plan
- View Plan Benefits

Plan changes should take effect according to the application's subscription policy.

---

# Billing Information

The Subscription section should display relevant billing information, including:

- Current billing status.
- Next billing date.
- Payment history (if applicable).

This information should remain accessible without affecting the user's content or account preferences.


---

# Application

The Application section provides access to general application information, legal documents, support resources, and account management actions.

These settings do not affect content generation or account preferences.

---

# Help & Support

Users should be able to access support resources when assistance is required.

Examples include:

- Help Centre
- Contact Support
- Report a Problem
- Submit Feedback

Support resources should remain accessible at all times.

---

# Legal

Users should be able to review Aura AI's legal documentation.

This section includes:

- Privacy Policy
- Terms of Service

These documents should always reflect the latest published version.

---

# About

The About section provides information about the installed application.

Examples include:

- Application Version
- Build Number

This information is intended for reference and troubleshooting purposes.

---

# Account Actions

The following account actions should be available:

### Sign Out

Signs the user out of Aura AI while preserving account data.

The user may sign in again at any time.

---

### Delete Account

Allows the user to permanently delete their Aura AI account.

Before deletion, the application should clearly inform the user that:

- The action is permanent.
- All associated account data will be permanently removed.
- Deleted data cannot be recovered.

Account deletion should require explicit user confirmation before proceeding.

---

# User Experience

The Application section should:

- Keep support resources easy to find.
- Present legal information clearly.
- Provide transparent account management options.
- Prevent accidental account deletion through confirmation steps.

Application settings should remain separate from creator preferences and subscription management.