# aws-secure-account-baseline

A beginner project where I set up an AWS account the way a real company would: the right people get only the access they need (least privilege).

## Goal
Learn how AWS IAM works by building it, breaking it on purpose, and documenting what happened.

## What I'm building
- Root user secured with MFA (and not used for daily work)
- An admin IAM user for daily work
- Groups: `Kitchen` (S3 full access) and `Cashiers` (S3 read-only)
- Users placed in groups, with no policies attached directly to people
- A custom JSON policy I wrote, limited to one S3 bucket
- A role with a trust policy and a permission policy
- A billing budget alert

## Experiments (build, break, explain)
| Experiment | What I predicted | What happened |
|---|---|---|
| Read-only user tries to delete a file | | |
| Move that user to a group with full access | | |
| Add an explicit Deny while they're in the full-access group | | |
| Remove the user from all groups | | |
| Use the wrong bucket name in my policy | | |

## What I learned
- (Write 3 things in your own words, for example how Allow and Deny interact)

## Mistakes I made and how I fixed them
- (Write 2 or 3 real ones as they happen)

## Screenshots
(Added in the `screenshots` folder)

## Security notes
No access keys, passwords, or account IDs are stored in this repo.

## Status
In progress. Started October 1, 2026.
