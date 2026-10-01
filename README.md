# AWS Secure Account Baseline

A beginner project to learn AWS IAM (Identity and Access Management) by building it, breaking it on purpose, and documenting what happened. The goal is least privilege: people get only the access they need.

> **Note:** Part 1 is based on a guided AWS IAM lab. Part 2 is my own version, built from scratch with my own groups and a custom policy.

## Part 1: Guided IAM lab (completed)
- Explored IAM users and groups
- Inspected IAM policies
- Followed a real-world scenario: adding users to groups with specific permissions
- Located and used the IAM sign-in URL
- Tested how policies change what a user can do in a service

## Part 2: My own build (in progress)
- [ ] Root user secured with MFA, not used for daily work
- [ ] Admin IAM user for daily work
- [ ] Groups: `Kitchen` (S3 full access) and `Cashiers` (S3 read-only)
- [ ] Users added to groups, with no policies attached directly to people
- [ ] Custom JSON policy limited to one S3 bucket (see `/policies`)
- [ ] Role with a trust policy (EC2) and a permission policy
- [ ] Billing budget alert

## Experiments (build, break, explain)
| Experiment | What I predicted | What happened (with real error message) |
|---|---|---|
| Read-only user tries to delete a file | Denied | |
| Move that user to a full-access group | Allowed | |
| Add an explicit Deny while in the full-access group | Denied | |
| Remove the user from all groups | Denied | |
| Use the wrong bucket name in my policy | Denied | |

## What I learned
- A policy is a permission slip; users, groups, and roles hold it
- Permissions from multiple groups add up
- An explicit Deny always beats an Allow
- With no Allow, access is denied by default
- A role has two policies: a permission policy (what it can do) and a trust policy (who can assume it)
- Roles give temporary credentials; users have long-term credentials

## Mistakes I made and how I fixed them
- **Confused roles with policies.** I thought a role could restrict a user who already had access through a group. It can't. Only removing the group or adding an explicit Deny takes access away.
- **Planned to work as the root user.** I learned to lock root with MFA and use an admin IAM user for daily work.
- **Assumed access was allowed by default.** IAM denies by default.

## Screenshots
Added in the `screenshots` folder.

## Security notes
No access keys, passwords, or account IDs are stored in this repo.

## Status
In progress. Started October 1, 2026. Guided lab done; custom build next.
