---
title: Week 3 - MFA
parent: Cybser_Security_Awareness_Month
nav_order: 2
layout: home
---

**********UNDER MAINTENANCE**********
This page describes MFA.

Why MFA is important

* A password that's simple and easy to remember is trivial for a computer to crack.
* Password breaches happen regularly, necessitating rotation.
* Reduces successful compromise by 99.9%[2]

---
How to enable MFA

Microsoft Account Security Settings: https://account.microsoft.com/
Security > Account > Manage how I sign in > Add a new way to sign in or verify > User an app

---
Types of MFA

* Phishing Prone (OTP/TOTP)
    * SMS 
    * Email code
    * Voice verification
    * Security questions with true answers. Lie, answer an unrelated question, or use a whimsical phrase. Q:Where were you born? A:I drive a hot air balloon these days.
        * Help Desk verifying these questions are looking for an answer match, not a true and valid response.

These are prone to phishing because the user is provided a short code, often 6 digits, that can be provided to an adversary if the user is caught off guard or is emotionally compromised. Another weakness, specifically to SMS, is threat actors are known to social engineer (vish) employees at Telecom companies, or in some cases bribe them, to gain access to a user's phone number in order to intercept the 6 digit code that can be used to compromise an account.

* Abuse Prone (Disruptive to normal device usage)
    * Approve/Deny push notifications
    * SMS
    * Voice verification

These are abuse prone because threat actors can use them to effectively perform a denial of service (DoS) against a device. Push notifications, if not managed, can trigger mobile device vibrations, chimes, and banners on the screen. Voice verification will start a phone call, which also triggers mobile device vibrations, ringtones, and takes up the entire screen. SMS codes, too, trigger mobile device vibrations, ringtones, and banner notifications. This is a legitimate tactic used by adversaries, called MFA fatigue. The idea is to annoy the user with notifications to such an extent that they approve the authentication request or slip up and approve the request instead of denying it. It's less common now, but in some cases where services didn't put proper limits in place, ader

One way to fight back against this type of abuse is to disable noisy notifications from MFA apps, put short code numbers on silent, and (if feasible) mute verification phone numbers and use them only when _you_ are authenticating. "But how do I know if someone is breaking into my account?" Simple: badge notifications. All three, MFA applications, SMS apps, and phone apps will all have that red dot on their icon showing a missed notification.

* Phishing Resistant
    * Hardware Key (USB-key, not TOTP generator)
    * Number-matching
    * Biometrics

What makes these phishing resistant is the lack of information that can be reasonably provided to an adversary. There are no codes or phrases that go along with either of these. They prompt for verification on the device logging in as well so there's no chance of abusive notifications! These are the best methods of MFA and ought to be used where supported. The largest drawback is the current lack of support for using hardware keys and biometrics for MFA.

---
Backup Codes

These are the emergency, break-glass method to access an account with MFA enabled.

Help Desks may not always be comfortable with or be able to properly verify identity and will advise to use backup codes when unable to login. This is something you'll want to write down and keep in a safe place. They are the only saving grace when unable to login with other MFA and backup methods.

---

Notes:

* SMS is weak due to Telco staff compromise
* 6-digit codes are phish-prone
* Key > App > Email
* Request sensitive accounts integrate app or key-based MFA and move from SMS
* Type of MFA used can be incredibly annoying when abused. Texted codes, voice verification, app notifications, etc. (Turn off MFA app notifications, open only when needed)
* **KEEP COPIES OF BACKUP CODES WRITTEN DOWN IN SAFE PLACE**


----
* [1] Why MFA - https://www.okta.com/identity-101/why-mfa-is-everywhere/
* [2] 
* [3] Large wordlist - https://www.troyhunt.com/introducing-306-million-freely-downloadable-pwned-passwords/
* [4] MFA fatigue - https://techcommunity.microsoft.com/t5/microsoft-entra-blog/defend-your-users-from-mfa-fatigue-attacks/ba-p/2365677
* [5] Disable Notifications - https://www.bleepingcomputer.com/news/security/mfa-fatigue-hackers-new-favorite-tactic-in-high-profile-breaches/
