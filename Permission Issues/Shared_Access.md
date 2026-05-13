# Shared Folder Issue



## Ticket Scenario

An HR employee reports that they can't access the shared HR Folder on the network drive.

---

## Problem

- `LAB\hruser2` attempts to access `\\DC01\HR_Share`
- Notification states that the user currently does not have permission to access the shared folder

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/af5ba90b-5d62-4c38-8812-42561eef48e1" />
---

## Fix

- `HR_Group` was not given permission Read/Write the HR_Share
- Under the `HR_Share` Properties interface, share the folder with `HR_Group` and provide R/W permissions.

---

## Verification

- Retest access from `CLIENT01` using `LAB/hruser2`

---

## Investigation Steps

1. Ping the Domain Controller 'DC01' to check if it's a DNS or IP issue
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/6a9f2fcb-ae7e-45f8-986a-11b5aa44befc" />

&nbsp;

2. Verify that `hruser2` is an active member of the HR_Group.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/7b94b999-f52b-4ddc-816b-29b755fc6d6b" />

&nbsp;

3. It's discovered that `HR_Group` has not been given the folder permissions.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/59551a0b-0c3f-42fd-b8d1-1fb7aebc8d26" />

&nbsp;

4. Add `HR_Group` to the list of people with Read/Write access for the `HR_Share` folder.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/1308af1a-db82-4234-a735-520fd9ae86f5" />

&nbsp;

5. Ensure that `HR_Group` has NTFS permissions.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/12698571-630e-4ab1-81dc-93096a189af7" />


