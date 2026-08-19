---
title: "Hong Kong SFC Moves Beyond OTP: Why Passkeys Are Becoming the New Standard for Internet Trading"
date: 2026-08-19
draft: false
description: "What the Hong Kong SFC's new cybersecurity requirements mean for OTP, phishing-resistant authentication and passkeys."
categories: Identity
tags: ["Passkey", "OTP", "SFC", "FIDO2"]
ShowToc: true
TocOpen: true
ShowReadingTime: true
ShowWordCount: true
---

## A Significant Change in Authentication

On 9 July 2026, the Hong Kong Securities and Futures Commission (SFC) issued a new circular requiring internet brokers and SFC-licensed virtual asset service providers (VASPs) to adopt robust, phishing-resistant authentication methods to protect clients' trading accounts.

One part of the circular immediately caught my attention:

> The SFC does not consider OTP to be a phishing-resistant authentication solution.

The SFC specifically says that internet brokers and VASPs should not use email OTPs or SMS OTPs for client login and device-binding processes.

Instead, the circular identifies **passkeys** and **bound devices** as examples of robust authentication solutions.

This is an important signal for the identity and authentication industry.

The question is no longer simply:

**"Do we have MFA?"**

It is becoming:

**"Is our authentication actually resistant to phishing?"**

---

## Why Is the SFC Making This Change?

The reason is straightforward: phishing attacks are still extremely effective.

According to the SFC, phishing accounted for 57% of the security incidents reported to the Hong Kong Computer Emergency Response Team Coordination Centre in 2025.

The SFC also described large-scale SMS phishing campaigns targeting clients of internet brokers and VASPs.

The attack pattern is familiar:

```text
Fake SMS
   ↓
Fake broker website
   ↓
User enters username/password
   ↓
User enters OTP
   ↓
Attacker captures the credentials
   ↓
Attacker gains access to the account
   ↓
Unauthorised transactions