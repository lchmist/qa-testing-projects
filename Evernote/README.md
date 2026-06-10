# Evernote Mobile Application Testing

## Project overview

This repository contains manual testing documentation for the Evernote mobile application.

The testing process was originally documented in Jira. Since access to the Jira project is time-limited, the most important information has been moved to this GitHub repository. The repository includes the testing checklist, a summary of reported defects, and evidence in the form of screenshots and videos.

## Tested application

**Application:** Evernote
**Platform:** Android mobile application
**Testing type:** Checklist-based manual testing
**Device:** Samsung Galaxy S20+ 5G
**Operating system:** Android 10
**Application version:** Evernote 11.19.2

## Scope of testing

The testing was based on the following checklist areas:

* Functional testing
* Performance testing
* Usability testing
* Compatibility testing
* Recoverability testing

The goal was to verify whether the Evernote mobile application works according to expected mobile application quality requirements, including application behavior after launch, background mode, navigation, network conditions, screen orientation, usability, performance, and recovery after interruptions.

## Repository structure

```text
.
├── README.md
├── checklist.md
└── evidence/
    ├── screenshots/
    │   ├── bug_01_large_attachment_mobile_data_jira.png
    │   ├── bug_02_landscape_more_menu_cut_jira.png
    │   └── bug_03_no_network_error_jira.png
    └── videos/
        ├── bug_01_large_attachment_mobile_data.mp4
        └── bug_03_no_network_error.mp4
```

## Reported defects

### Bug 01 — Application does not display any warning when downloading a large attachment using mobile data

**Checklist area:** Usability checklist
**Priority:** Medium
**Environment:** Samsung Galaxy S20+ 5G, Android 10, Evernote 11.19.2

**Steps to reproduce:**

1. Open the application.
2. Ensure mobile data is enabled and WiFi is disabled.
3. Download a file of approximately 129 MB.
4. Observe the download process.

**Expected result:**
The user should receive a warning or confirmation dialog before downloading a large attachment using mobile data.

**Actual result:**
The file downloads without any warning or confirmation about high mobile data usage.

**Evidence:**

* [Jira screenshot](evidence/screenshots/bug_01_large_attachment_mobile_data_jira.png)
* [Video attachment](evidence/videos/bug_01_large_attachment_mobile_data.mp4)

---

### Bug 02 — Landscape orientation cuts off top of "More" menu

**Checklist area:** Compatibility checklist
**Priority:** Medium
**Environment:** Samsung Galaxy S20+ 5G, Android 10, Evernote 11.19.2

**Steps to reproduce:**

1. Open the application.
2. Rotate the device to landscape mode.
3. Tap the "More" button.
4. Observe the menu position.

**Expected result:**
The full "More" menu should be visible and accessible within the screen boundaries in landscape orientation.

**Actual result:**
The top part of the "More" menu is cut off and cannot be accessed properly.

**Evidence:**

* [Jira screenshot](evidence/screenshots/bug_02_landscape_more_menu_cut_jira.png)

---

### Bug 03 — No error message is displayed for network-dependent actions while offline

**Checklist area:** Functional checklist
**Priority:** Medium
**Environment:** Samsung Galaxy S20+ 5G, Android 10, Evernote 11.19.2

**Steps to reproduce:**

1. Disconnect from the internet or switch to offline mode.
2. Open the application.
3. Try to perform an action that requires an internet connection, for example synchronization, downloading an attachment, or opening online content.
4. Observe the application behavior.

**Expected result:**
The application should display a clear error message, for example: "Network error. Please try again later."

**Actual result:**
No network error message is displayed after performing a network-dependent action while offline.

**Note:**
The application may support offline mode, but the user should still receive clear feedback when an action cannot be completed due to lack of internet connection.

**Evidence:**

* [Jira screenshot](evidence/screenshots/bug_03_no_network_error_jira.png)
* [Video attachment](evidence/videos/bug_03_no_network_error.mp4)

## Notes

The original Jira project was used to manage and report this testing task. Due to limited access to Jira, screenshots, videos, and descriptions of the reported issues are included in this repository as evidence of completed work.


