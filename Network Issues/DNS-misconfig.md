# Network Issue



## Scenario
A member of the HR Department is having difficulty logging into their account using the CLIENT01 machine. It's displaying an error message saying that the domain isn't available and to check whether the device is connected to the network

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/3f168ce8-124d-4e86-9cd7-88191f5e0a8d" />

&nbsp;

<img width="700" height="227" alt="image" src="https://github.com/user-attachments/assets/b13571ff-d1e9-4edb-9eda-1bca243d7296" />


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


