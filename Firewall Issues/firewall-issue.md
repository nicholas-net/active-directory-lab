How do I recognize that firewall is the issue?

## Scenario
- IT administrator is unable to access `CLIENT01` via Remote Desktop after firewall configuration changes.
## Symptoms
- IT Administrator is presented with a list of potential explanations for the error that has occured
  - Server is unavailable
  - Remote computer is turned off
  - Remote computer is unavailable on the network

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/b555d383-701e-46d4-876c-90474aedc177" />

## Investigation
- Let's test to see if `CLIENT01` is reachable on the network.
- I use the `ping` command send ICMP packets to the IPv4 address of `CLIENT01`.
- No packet loss occured so it appears that the device available on the network.
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/2220c76d-7590-4943-81da-d6a44ada402e" />

&nbsp;

- Additionally using `ping`, I test to see if there is any issue with the devices DNS resolution.
- That does not appear to be the case based on the response from `CLIENT01`.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/690d38df-395d-4a25-ac95-8d224ae636a9" />


## Root Cause
## Resolution
## Verification
