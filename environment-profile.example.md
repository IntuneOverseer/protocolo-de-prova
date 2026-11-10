# Environment profile (FICTIONAL EXAMPLE)

Português: [perfil-ambiente.exemplo.md](perfil-ambiente.exemplo.md)

> This is a template. Every name, domain and address below is invented (domains and IPs reserved for documentation).
> Your real profile is **yours**: keep it local, do not publish it, do not paste it into a ticket and **never** put passwords, tokens or keys here.
> Only `[declared]` facts (you said so) or `[proven]` facts (a command showed it) go in. No assumptions.

## Execution

- `[declared]` Administrative workstation: `admin-station-01` (production, daily use).
- `[proven]` Main shell: PowerShell 7.x (confirmed with `$PSVersionTable`).
- `[declared]` Administrative account: `admin.example@example.com`.
- `[declared]` Privileges: local administrator on the workstation; administrative roles as the task requires.

## Servers and layers

| Role | Machine | Shell | Use | Note |
|---|---|---|---|---|
| Directory (read) | `dc-read-01.example.com` | Windows PowerShell 5.1 | Evidence collection, no writes | `[declared]` |
| Directory (write) | `dc-write-01.example.com` | Windows PowerShell 5.1 | Changes, with delegation | `[declared]`; validate the token before changing |
| Update server | `srv-update-01.example.com` | Windows PowerShell 5.1 | Read or change, always declare | `[declared]` |

## Lab (ER Module and Lab Gate)

- `[declared]` Linux lab: `lab-linux-01` (VM, with snapshot).
- `[declared]` Windows lab: `lab-win-01` (VM, with snapshot).
- `[declared]` Test mobile device: `test-tablet-01`.
- `[declared]` Lab network isolated from production.

## Restrictions and policies

- `[declared]` `AllSigned` execution policy on the administrative workstation: scripts must be signed.
- `[declared]` The organization's code cannot be sent to external services without approval.
- `[declared]` Personal projects are kept completely separate from the organization's environment.

## Working preferences

- `[declared]` Command output saved to a text file and opened in Notepad when copy and paste is not possible.
- `[declared]` Files sent by the assistant go to `C:\Users\example\Downloads`.

## Mechanisms mapped in this environment (grows with use)

- `[proven]` Example: an unsigned script is blocked by the `AllSigned` policy; signing the script fixes it without touching the policy. *(Evidence: signature error output and a successful run after signing.)*

## How the assistant uses this file

1. Reads the profile at the start of the session (or you paste the contents).
2. Confirms with you only what is outdated or missing.
3. Proposes **adding** new facts, showing exactly what it would write. You approve.
4. If current evidence contradicts the profile, the evidence wins and the profile is corrected.
