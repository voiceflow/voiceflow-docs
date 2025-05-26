---
title: Domain Whitelisting Implementation Guide
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
## Overview

This document outlines the implementation of domain whitelisting for web chat widgets. Domain whitelisting allows you to restrict which domains can load and interact with your chat widget, providing an additional layer of security and control over your chat deployment.

## Implementation Steps

### 1. Configuring Allowed Domains

Each chat widget instance can be configured with a list of allowed domains. Domains can be specified in the below formats:

- Exact match domains (example.com)
- Subdomain wildcards (\*.example.com)

### 2. Runtime Verification

Our system automatically handles domain verification at runtime:

- When a user loads your webpage, our widget checks the current domain
- The domain is verified against your configured allowlist
- Access is granted or denied based on the verification result
- No additional code changes are needed on your end

### 3. Security Considerations

Domain whitelisting provides several security benefits:

- Prevents unauthorized embedding of your chat widget
- Reduces potential abuse from unknown domains
- Helps maintain brand consistency

While domain whitelisting is a strong security measure, it works best as part of a comprehensive security strategy.

### 4. Best Practices

1. Start with a restrictive allowlist and add domains as needed
2. Include all relevant subdomains
3. Regularly audit your allowed domains

### 5. Troubleshooting

Common scenarios you might encounter:

1. Widget not loading:
   - Verify the domain is correctly whitelisted
   - Check for exact matches including protocol if specified

2. Subdomain access issues:
   - Confirm wildcard patterns are correctly formatted
   - Verify the subdomain pattern matches your actual domain structure