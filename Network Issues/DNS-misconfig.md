# Network Issue



## Scenario
A member of the HR Department is having difficulty logging into their account using the CLIENT01 machine. It's displaying an error message saying that the domain isn't available and to check whether the device is connected to the network

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/3f168ce8-124d-4e86-9cd7-88191f5e0a8d" />

&nbsp;

<img width="700" height="227" alt="image" src="https://github.com/user-attachments/assets/b13571ff-d1e9-4edb-9eda-1bca243d7296" />


---

## Problem

- HR employee reports not being to access their account `hruser2` on `CLIENT01`.
- Employee has indicated that other members of the team also cannot access their account on `CLIENT01`.

---

## Cause



---

## Fix


---

## Verification

---

## Troubleshooting

1.) Ping `CLIENT01` to test if its reachable on the network

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/529d6e7b-7e95-447f-9b03-025bd7924ed5" />

- What does this  mean?
  - This could indicate that the host is powered off, but we know this isn't the case
  - This could mean that their is a name resolution problem (CLIENT01 isnt being mapped to the IP)
  - Firewall is blocking the ICMP request

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/43a867eb-7145-40dc-b07f-186b03d3ebdf" />




