# AWS IAM Guided Lab

A hands-on lab where I learned AWS IAM (Identity and Access Management): how users, groups, and policies control who can do what in an AWS account.

> This project is based on a guided AWS IAM lab. It documents what I did and what I learned.

## What I did
- Explored IAM users and groups
- Inspected IAM policies
- Followed a real-world scenario: adding users to groups with specific permissions
- Located and used the IAM sign-in URL
- Tested how policies change what a user can do in a service

## Experiments
| Experiment | What I predicted | What happened |
|---|---|---|
| Read-only user tries to delete a file | Denied | Denied |
| Move that user to a group with full access | Allowed | Allowed |
| Add an explicit Deny while in the full-access group | Denied | Denied |
| Remove the user from all groups | Denied | Denied |
| Use the wrong bucket name in my policy | Denied | Denied |

## What I learned
- A policy is a permission slip; users, groups, and roles hold it
- Permissions from multiple groups add up
- An explicit Deny always beats an Allow
- With no Allow, access is denied by default
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
Completed October 1, 2026.
