---
title: Workflows
layout: home
---

Drive-by download
    Check triggering domain. 
        Check if associated C2 domain visited.
    Check if file downloaded (Object creation, file write)
    Check if file run (Process start, process execution)
    Check if file prevented from running (AppLocker, Defender, EDR log)
    If all conditions unmet, close alert and add to report.
    If compromise condition(s) met, begin response procedures.

Identity
    Title-based RBAC
    Certificate-based MFA
    Passkey if that's actually a thing

