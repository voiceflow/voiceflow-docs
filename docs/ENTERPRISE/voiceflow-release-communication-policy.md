---
title: Voiceflow Release Communication Policy
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Introduction

This document outlines the policies and procedures for communicating new releases and updates to Voiceflow's platform. Special attention is given to Private Cloud customers who operate on a different release cadence.

## Release Cadence

### Public Cloud

- **Release Frequency**: Updates and new features are released to the Public Cloud on a regular basis.
- **Communication**: Release notes and update details are communicated on our public changelog (changelog.voiceflow.com), including, when appropriate, email notifications, in-app notifications, and our online documentation.

### Private Cloud

- **Release Frequency**: Private Cloud customers have the option to choose their synchronization frequency with the Public Cloud. By default, synchronization occurs every Saturday at 11 AM EST.
- **Customization**: Customers can select how often to sync and schedule their sync times. However, this schedule is not adjustable on a per-feature or on-demand basis.

## Key Policies

### Communication of Releases

- **Notification**: At the time of any feature release, detailed release notes will be provided in the changelog. These will include information on new features or enhancements.
- **Advance Notice**: For any significant changes or deprecations, we will provide at least two weeks notice to ensure customers have ample time to prepare.
- **Channels**: Communications will be made through our public changelog (changelog.voiceflow.com), email, in-app notifications, and our online documentation.

### Legacy Project Support

- **Deprecation Policy**: Legacy components will only exist if functionality is fully deprecated without migration options. Customers will be notified at least two weeks in advance.
- **Project Compatibility**: Projects on the Private Cloud will not be considered legacy as long as they remain unsynced with new features released to the Public Cloud. Projects will continue to operate based on the version of the platform they are currently using.

## Example Scenario

1. **Public Cloud Release**: A new feature, Feature X, is released.
2. **Public Cloud Impact**: All projects on the Public Cloud are migrated to use Feature X.
3. **Private Cloud Scenario**: For Private Cloud customers, Feature X will not be applicable until their next scheduled sync with the Public Cloud.

## Important Considerations for Private Cloud Customers

- **Sync Delays**: While customers can choose their sync frequency, delaying synchronization is not recommended as it may prevent timely patches for bugs or security issues.
- **Customization Limitations**: The synchronization schedule cannot be easily adjusted on a per-feature or on-demand basis.
- **Security and Compliance**: Ensuring timely synchronization is crucial for maintaining security and compliance standards. Delayed updates may expose customers to vulnerabilities.

## Responsibilities

### Voiceflow's Responsibilities

- **Timely Updates**: Ensure that all updates, including security patches and critical bug fixes, are prepared and communicated in a timely manner.
- **Support**: Provide support and guidance to customers regarding updates, synchronization schedules, and any potential impacts on their projects.
- **Documentation**: Maintain up-to-date and comprehensive documentation on release notes, update schedules, and migration guides.

### Customer Responsibilities

- **Schedule Management**: Private Cloud customers must manage their synchronization schedules and ensure they align with their operational requirements.
- **Communication**: Stay informed by regularly checking email notifications, in-app messages, and Voiceflow's online documentation for updates.
- **Compliance**: Adhere to security and compliance recommendations by synchronizing regularly to receive the latest patches and updates.

## Additional Information

For any questions or further assistance, please contact our support team.