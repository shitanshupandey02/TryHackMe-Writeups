# TryHackMe-Writeups
# TryHackMe: Alert Triage — Write-up

<img width="1488" height="563" alt="Screenshot 2026-06-26 233820" src="https://github.com/user-attachments/assets/856d00b6-2d7d-475c-bd65-f4ecea989eee" />

## 📌 Room Overview
* **Room Link:** [TryHackMe - SOC L1 Alert Triage](https://tryhackme.com/room/socl1alerttriage)
* **Category:** Blue Team / Security Operations Center (SOC) Level 1
* **Objective:** Learn how to prioritize, investigate, and handle security dashboard alerts using standard industry playbooks.

## 🛠️ Concepts & Skills Learned
* **Alert Prioritization:** Sorting by severity (Critical, High, Medium, Low) and timestamp (oldest first).
* **Incident Lifecycle:** Moving an alert from `New` ➡️ `In Progress` ➡️ `Closed`.
* **Verdict Determination:** Distinguishing between True Positives (TP) and False Positives (FP).
* **Investigation Workflow:** Tracking malicious activity back to specific hostnames, users, and Indicators of Compromise (IoCs).

## 🔍 Investigation Walkthrough

### Task 1: Sorting and Assignment
* Explain the rationale behind picking the first alert (e.g., filtering out already assigned events, picking highest severity, prioritizing older timestamps to mitigate ongoing breaches).
* **Action taken:** Assigned the alert to myself and updated status to "In Progress".

### Task 2: Alert Analysis (True Positive vs False Positive)
*Describe how you triaged the suspicious alerts without including the direct room flags.*

#### Case 1: Phishing and Malware Delivery Attempt
* **Indicators Reviewed:** [e.g., Suspicious file hash, double-extension executables like `cats2025.mp4.exe`, or malicious lookalike domains]
* **Analysis:** Chrome browser downloaded a double-extension file from an unknown external IP address.
* **Verdict:** **True Positive (Malicious)**. 
* **Resolution:** Left an analyst comment detailing the timeline and closed the alert.

#### Case 2: GitHub Framework Download
* **Indicators Reviewed:** [e.g., Access to github.com/facebook/react by a developer asset]
* **Analysis:** Evaluated a low-severity alert where a user profile inside the developer network accessed an official software repository.
* **Verdict:** **False Positive (Benign)**. This constitutes normal developer baseline behaviour.

## 💡 Defensive Takeaways
1. **Playbook Efficiency:** Following a standard operating workbook prevents analyst alert fatigue.
2. **Context Matters:** A developer pulling from GitHub is noise, but a finance user running an executable from an untrusted external link is an active incident.

