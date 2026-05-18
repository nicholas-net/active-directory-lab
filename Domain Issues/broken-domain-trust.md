## Scenario

I wanted to learn about the differences between workgroups and Active Directory, so this lab goes hands on by breaking the trust between `CLIENT01` and the domain `lab.local`. 

## Action
- Removed `CLIENT01` from the `lab.local` domain
- Made `CLIENT01` a member of the workgroup `TEAMX`

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/c74cda77-c273-4c38-b48e-dd3a768f0e27" />

## Problem Observed
- `CLIENT01` is no longer authentication to access resources and serves being provided by `DC01`.
- Attempting to access the `DC01` requires re-authentication

&nbsp;

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/413b4b32-39d8-4f91-9871-245ff8d547b6" />

## Cause
- The disruption occurred because CLIENT01 was removed from the lab.local domain and no longer had a trust relationship with Active Directory.

## Fix
- Rejoining a `lab.local` domain and rebooting `CLIENT01 will restore `CLIENT0` authentication.

## Verification
- Verified current login using whoami
<img width="433" height="106" alt="image" src="https://github.com/user-attachments/assets/87ea1922-d0bd-472b-9c83-1052e189a884" />

## EXTRA: Powershell Solutions

- Remove `CLIENT01` from the domain and later rejoin it to `lab.local`.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/33b556fc-fb07-46a3-92a9-164dcc8a0972" />

&nbsp;

- Add `CLIENT01` back to the `lab.local` domain

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/9a96dd61-6d75-4e96-a8f4-1e4501f3cd1b" />








