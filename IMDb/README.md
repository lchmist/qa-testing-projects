
# IMDb Mobile Application Testing

## Project overview

This repository contains manual testing documentation for the IMDb mobile application.

The testing process was originally documented in Jira. The most important information has been moved to this GitHub repository. The repository includes the testing checklist, a summary of reported defects, and evidence in the form of screenshots and videos.

## Tested application

**Application:** IMDb
**Platform:** Android mobile application
**Testing type:** Checklist-based manual testing
**Device:** Samsung Galaxy S20+ 5G
**Operating system:** Android 13
**Application version:** 9.3.2.03

## Scope of testing

The testing was based on the following checklist areas:

* Functional testing
* Performance testing
* Usability testing
* Compatibility testing
* Recoverability testing

The goal was to verify whether the IMDb mobile application works according to expected mobile application quality requirements, including application behavior after launch, background mode, navigation, network conditions, screen orientation, usability, performance, login/registration behavior, and recovery after interruptions.

## Repository structure

```text
.
├── README.md
├── checklist.md
└── evidence/
    ├── screenshots/
    │   ├── bug_01_no_clear_internet_connection_message_jira.png
    │   └── bug_02_insecure_password_policy_jira.png
    └── videos/
        └── bug_01_no_clear_internet_connection_message.mp4
```

## Reported defects

### Bug 01 — No clear information about missing internet connection is displayed

**Checklist area:** Functional checklist
**Priority:** Medium
**Environment:** Samsung Galaxy S20+ 5G, Android 13, IMDb, version 9.3.2.03

**Steps to reproduce:**

1. Disable internet connection on the device.
2. Open the IMDb application.
3. Perform an action that requires an internet connection.
4. Observe the displayed message.

**Expected result:**
The application should clearly inform the user that there is no internet connection.

**Actual result:**
The application displays a generic error message instead of clearly informing the user that the device is offline.

**Note:**
The message does not clearly explain that the issue is caused by missing internet connection, which may confuse the user.

**Evidence:**

* [Jira screenshot](evidence/screenshots/bug_01_no_clear_internet_connection_message_jira.png)
* [Video attachment](evidence/videos/bug_01_no_clear_internet_connection_message.mp4)

---

### Bug 02 — Insecure password policy allows users to register with easily guessable passwords

**Checklist area:** Functional checklist / Security
**Priority:** Medium
**Environment:** Samsung Galaxy S20+ 5G, Android 10, IMDb, version 9.3.2.03

**Steps to reproduce:**

1. Open the IMDb application.
2. Go to the registration screen.
3. Enter valid registration data.
4. Enter a simple 6-character password, for example: "123456" or "aaaaaa".
5. Submit the registration form.

**Expected result:**
The application should prevent users from creating accounts with easily guessable passwords or should require a more secure password format.

**Actual result:**
The application accepts any 6-character password. The only displayed requirement is a minimum length of 6 characters.

**Note:**
No explicit password complexity requirement was provided. However, allowing users to register with any 6-character password may be insecure, because passwords such as "123456" or "aaaaaa" are easy to guess and may increase the risk of unauthorized account access.

**Evidence note:**
Screenshots and screen recording are blocked by the application on the registration screen, so visual evidence could not be attached. The issue was verified manually during testing.

**Evidence:**

* [Jira screenshot](evidence/screenshots/bug_02_insecure_password_policy_jira.png)

## Performance observation

CPU usage was observed during manual testing. CPU usage was approximately 32% before the test and increased to around 40% during active app usage, with temporary peaks up to 44%. This behavior was considered acceptable because the increase occurred during user interaction and no sustained abnormal CPU usage was observed.

No obvious memory leak symptoms, abnormal battery drain, or device overheating were observed during the manual test session.

## Notes

The original Jira project was used to manage and report this testing task. Due to limited access to Jira, screenshots, videos, and descriptions of the reported issues are included in this repository as evidence of completed work.
