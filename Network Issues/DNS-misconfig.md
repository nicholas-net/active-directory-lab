# Network Issue



## Scenario
A member of the Sales Department is having difficult connecting to the network.

---

## Problem



---

## Cause



---

## Fix


---

## Verification

---

## Troubleshooting

Initially, `CLIENT01` told me that the user `LAB\salesuser2` wasn't permitted to log in remotely. Using the `DC01`, I opened Active Directory Users and Computers and added `Sales_Group` to `Remote Desktop Users`. I re-attempted to enter credentials, and it allowed me access.

<img width="531" height="207" alt="image" src="https://github.com/user-attachments/assets/5d21fe43-08e8-44a3-a5d2-86242f64b7c0" />


