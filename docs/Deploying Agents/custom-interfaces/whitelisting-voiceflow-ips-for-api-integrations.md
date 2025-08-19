---
title: Whitelisting Voiceflow IPs for API Integrations
excerpt: >-
  Whitelist Voiceflow’s public outbound IP addresses when connecting to a
  firewall-protected or geo-restricted API.
deprecated: false
hidden: true
metadata:
  robots: index
---
## Whitelisting Voiceflow IPs for API Access

Some APIs restrict access based on the originating IP address for security or compliance reasons. If your custom API returns `403 Forbidden` or is inaccessible when called from Voiceflow, you may need to whitelist the static outbound IPs used by Voiceflow’s cloud infrastructure.

***

### Voiceflow outbound IPs

Add **all** of the IPs below to your API’s allowlist / firewall rules:

* `35.172.149.91`
* `35.174.43.40`
* `50.16.0.201`

<br />

### When to whitelist

Whitelist Voiceflow’s IPs if:

* Your API is **restricted by geography or firewall**
* You require **static originating IPs** to allow external requests
* Your API calls return a **403**, **401**, or similar when triggered inside Voiceflow
* You are calling the API from a **Voiceflow Integration tool** or **API step** (hosted by Voiceflow)

<br />

### Configuration steps

1. Ask your security or API team to add Voiceflow’s IPs to their permitted inbound access list.
2. Confirm your endpoint allows **HTTPS traffic** from these IPs.
3. Retry the API call from your Voiceflow project.
4. Use the Logs tab or transcripts to confirm a successful response.

<br />

### Best Practices

* Provide the full IP range to your client or network admin up front.
* If using both **Development** and **Production** environments, confirm both are allowed.
* Ensure your endpoint uses **HTTPS** and has rate limits to prevent abuse.
* Re-test after whitelisting, then monitor for changes to API behavior or quotas.