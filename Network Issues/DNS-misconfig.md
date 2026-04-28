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

- `CLIENT01` IPv4 and DNS Server misconfigured with the wrong address.

---

## Fix

- Manually go into the Network Adapater Settings and re-configure the IPv4 and DNS with the correct address.

---

## Verification

- nslookup confirmed DNS resolution for CLIENT01 using the updated configuration.
- ICMP was used to verify basic network connectivity between `DC01` and `CLIENT01`.
---

## Troubleshooting

1.) Ping `CLIENT01` to test reachability, and when that failed I pinged the manually assigned IP address as well.

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/529d6e7b-7e95-447f-9b03-025bd7924ed5" />

&nbsp;

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/7b6600c5-2614-43e2-9a60-46798b2acdd8" />

&nbsp;

- What does this  mean?
  - This could indicate that the host is powered off, but we know this isn't the case.
  - This could mean that their is a name resolution problem (CLIENT01 isnt being mapped to the IP).
  - Firewall is blocking the ICMP request.

2.) Check if DNS name resolution is healthy on the server side.

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/f7876d6f-1b80-46b8-bb64-783d579165f1" />

&nbsp;

3.) Use the `nslookup` tool to test DNS resolution.

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/43a867eb-7145-40dc-b07f-186b03d3ebdf" />

&nbsp;

4.) Login to `CLIENT01` using local admin credentials and check Network Adapter Settings.

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/67c3c3e4-349e-4a6d-ba31-392a774cfbaa" />

&nbsp;

5.) IPv4 and DNS Server are observed to have been misconfigured with an extra 0 in the third octet.

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/eb55cc5b-2918-4ba2-b01c-a055f3eae0e3" />

&nbsp;

6.) Re-configure the IPv4 and DNS Server to the correct addresses and re-test the DNS resolution

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/417f008a-7735-42aa-a8ac-2f285244f064" />

&nbsp;

7.) Ping `CLIENT01` to test reachability

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/9286053e-bee0-401e-b4b3-ee68c6e5b137" />



