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

- Additionally using `ping`, I test to see if its reachable via it's domain name.
- That does not appear to be the case based on the response from `CLIENT01`.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/690d38df-395d-4a25-ac95-8d224ae636a9" />

&nbsp;

- Using `ipconfig /all` on `CLIENT01`under the lab.local admin account, I check to make sure the DNS server, IP address and subnet mask are configured correctly. 

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/24a153d2-7403-4709-8395-e412b4c0a919" />

&nbsp;

- Next, I load up the Windows Firewall to check the inbound configuration.
- I observe that `Remote Desktop - User Mode` for `TCP` and `UDP` inbound connections are both disabled.

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/7c9f2c27-d061-4b67-a813-ea6062c320c4" />

&nbsp;

- Additionally, I ensure that Remote Connections from this device are enabled in the System Properties.
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/c5c86f5a-f36a-4c6e-885c-55555b77a0be" />


## Root Cause
- `Remote Desktop - User Mode (TCP-In)` and `Remote Desktop - User Mode (UDP-In)` inbound firewall rules were disabled on `CLIENT01`, preventing Remote Desktop connections

## Resolution
- Enabled the `Remote Desktop - User Mode (TCP-In)` and `Remote Desktop - User Mode (UDP-In)` inbound firewall rules in Windows Defender Firewall on `CLIENT01`.
- Verified that Allow remote connections to this host was enabled in System Properties.
- Retested the Remote Desktop connection and confirmed successful access to `CLIENT01`.
## Verification

## EXTRA: PowerShell Solution
- Enable Remote Desktop Inbound Connections on `CLIENT01`

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/04fa2ce3-578e-4a72-a5e8-800435374d23" />

