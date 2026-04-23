# User Account Disabled

## Scenario

A member of the HR department is having difficulty logging into their account that belongs to the `lab.local` domain

As IT support, I first identify the scope of the issue by confirming when the problem began, the last successful login, and whether other users are affected. I then check for any error messages reported by the user. The user reports the message “Your account has been disabled.” I then proceed to Active Directory Users and Computers to investigate the account status. 

---

## Problem

- User could not log into `LAB\hruser1`.
- Error message: `Your account has been disabled. Please see your system administrator`.

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/e07c3701-e235-429a-9731-12d054b686ed" />

---

## Cause

- `LAB/hruser1` is disabled the Active Directory Users and Computers.

 <img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/2e3eff95-19a2-450a-bbc3-d73cabd16ed5" />

---

## Fix
- Use the Common Queries function in the AD to pull up the disabled accounts.
- Right Click the disabled HR employees account and re-activate.

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/540825c9-d3c3-4c12-9d0e-54708b5fa835" />

&nbsp;

- As a precaution, I reset the accounts password with a temporary password.
- `hruser1` must configure new login credentials next sign-in.

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/784d0507-6da6-4248-93d8-4a7114e26130" />

---

## Verification

- HR employee successfully logged into `hruser1` using updated credentials.
- The AD interface confirms that the `hruser1` account is activated.
