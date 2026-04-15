<p align="center">
<img width="562" height="182" alt="Screenshot 2026-04-14 195018" src="https://github.com/user-attachments/assets/93bacb1e-c33d-4b0e-9ac1-bb490a281828" />
</p>
<h1><u>Milestone 9: Branch 1 Route/Switch</u></h1>
    <p>Eighth phase, we will install 1 CISCO2911/K9 router with ipbasek9, and uck9 licensing. This router will act as the Branch 1 gateway providing access back to HQ and Branch 2 via the Private WAN and function as the local call controller and PSTN gateway. In addition, consultant will install a Cisco WS-C2960-24TT layer 2 access switch.</p>
    <h2><strong><u>Configuration Steps</u></strong></h2>
    <p><b>Step 1: Install And Configure The Branch 1 Router</b></p>
        <p>- A. Rack, Mount, And Power On The Cisco 2911 Router</p>
        <p>- B. Install Uck9 License</p>
        <p>- C. Basic Router Configurations (Hostname, NTP, Domain-Name, SSH, Etc)</p>
        <p>- D. Configure And Connect Branch 1 LAN Interface G0/0</p>
            <p>- I. MGMT Interface VLAN 100</p>
            <p>- II. Data Interface VLAN 192</p>
            <p>- III. Voice Interface VLAN 10</p>
        <p>- E. Configure DHCP Services For Branch 1 Data And Voice Networks</p>
            <p>- I. Address Exclusions</p>
            <p>- II. DHCP Pool B1-DATA</p>
                <p>- 1. Network</p>
                <p>- 2. Default-Router</p>
                <p>- 3. DNS Server</p>
            <p>- III. DHCP Pool B1-VOICE</p>
                <p>- 1. Network</p>
                <p>- 2. Default-Router</p>
                <p>- 3. Option 150 IP</p>
        <p>- F. Configure And Connect Private WAN Interface G0/1</p>
            <p>- I. IP Address</p>
            <p>- II. Disable CDP</p>
        <p>- G. Configure The New AP With A Unique SSID (GUEST), Channel, And Passphrase Using WPA2-PSK And AES</p>
        <p>- H. Install A Wireless Tablet And Configure It With The Same SSID And Passphrase.</p>
        <p>- I. Once The New Wireless Tablet Is Connected Confirm It Has Access To The Internet, But CANNOT Access Any Of The Corporate Networks</p>
        <p>- J. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- K. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- L. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- M. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- N. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- O. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- P. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- Q. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- R. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- S. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- E. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- E. Configure And Connect Branch 1 LAN Interface G0/0</p>
        <p>- E. Configure And Connect Branch 1 LAN Interface G0/0</p>
    <p><b>Step 2: Install And Configure Guest Wireless Access</b></p>
        <p>- A. On The HQ Server Configure The DHCP Scope For The Guest Network</p>
            <p>- I. Default Gateway</p>
            <p>- II. DNS Server</p>
            <p>- III. Starting IP Address</p>
            <p>- IV. Subnet Mask</p>
            <p>- V. Number Of DHCP Users</p>
        <p>- B. On HQ Core Switches 1 And 2 Configure An Access-List That Only Allows DHCP And Internet Traffic For The Guest Network And Blocks All Other Traffic</p>
        <p>- C. On The HQ Core Switches 1 And 2 Apply The New Access-List To The VLAN 172 Interface</p>
        <p>- D. On The HQ Core Switch 1 And 2 Configure IP Helper In The VLAN 172 Interface</p>
        <p>- E. Configure A Switchport On HQ Access Switch 3 To Be A Member Of VLAN 172 (Guest)</p>
        <p>- F. Install A New AccessPoint-PT And Connect It To The Newly Configure Switchport On HQ Access Switch 3</p>
        <p>- G. Configure The New AP With A Unique SSID (GUEST), Channel, And Passphrase Using WPA2-PSK And AES</p>
        <p>- H. Install A Wireless Tablet And Configure It With The Same SSID And Passphrase</p>   
        <p>- I. Once The New Wireless Tablet Is Connected Confirm It Has Access To The Internet, But CANNOT Access Any Of The Corporate Networks.</p>
        <h2><strong><u>Implementation</u></strong></h2>
        <h3>Step 1: Install And Configure Corporate Wireless Access</h3>
            <p>- A. Install An AccessPoint-PT And Connect It To HQ Core Switch 2 Into An Access Port.</p>
            <p>- First, we will install a wireless access point to connect corporate wireless users to the data network.</p>
                <img width="939" height="884" alt="Screenshot 2026-04-14 181638" src="https://github.com/user-attachments/assets/ddb4e5c1-6c5b-40ee-a2c3-4494b93e067a" />\
            <p>- B. Configure The New AP With A Unique SSID, Channel, And Passphrase Using WPA2-PSK And AES</p>
                <img width="866" height="885" alt="Screenshot 2026-04-14 181922" src="https://github.com/user-attachments/assets/4d696d46-e485-46e1-a112-dbbe977ac824" />
            <p>- C. Install A Wireless Tablet And Configure It With The Same SSID And Passphrase</p>
                <img width="940" height="883" alt="Screenshot 2026-04-14 182154" src="https://github.com/user-attachments/assets/624c65b9-7f08-4157-98e6-6f0249f51f05" />
                <img width="867" height="882" alt="Screenshot 2026-04-14 182226" src="https://github.com/user-attachments/assets/b2acf45e-39ca-4fff-a4e0-bb92bfe43910" />
            <p>- D. Once The New Wireless Tablet Is Connected Confirm It Has Access To The Corporate Networks And Internet</p>
                <img width="871" height="1574" alt="Screenshot 2026-04-14 182528" src="https://github.com/user-attachments/assets/6da25638-1070-4782-bed2-610c6fb3fd56" />
                <img width="526" height="591" alt="Screenshot 2026-04-14 182621" src="https://github.com/user-attachments/assets/6a484e11-2c30-4624-b74c-2f0d957b64f5" />
            <p><em>- Successful.</em></p>
        <h3>Step 2: Install And Configure Guest Wireless Access</h3>
            <p>- A. On The HQ Server Configure The DHCP Scope For The Guest Network</p>
                <p>- For this step, we will process with adding the guest network DHCP scope to the HQ-Server.</p>
                <img width="872" height="877" alt="Screenshot 2026-04-14 183054" src="https://github.com/user-attachments/assets/383b69cf-e7a1-44ea-b6f9-05225a30097f" />
            <p>- B. On HQ Core Switches 1 And 2 Configure An Access-List That Only Allows DHCP And Internet Traffic For The Guest Network And Blocks All Other Traffic</p>
                <p>- For this step, we will configure an ACL and DHCP helper on both core switches to prepare for guest wireless access.</p>
                <img width="872" height="494" alt="Screenshot 2026-04-14 183929" src="https://github.com/user-attachments/assets/974d50d0-13e0-4363-9b1c-aa05f8c7be7f" />
                <img width="864" height="498" alt="Screenshot 2026-04-14 184215" src="https://github.com/user-attachments/assets/8f662444-589e-407a-a211-fb85be8b695e" />
            <p>- C. On The HQ Core Switches 1 And 2 Apply The New Access-List To The VLAN 172 Interface</p>
                <img width="871" height="287" alt="Screenshot 2026-04-14 184435" src="https://github.com/user-attachments/assets/5015bf7d-9895-434c-9902-6745e03bc5b4" />
                <img width="871" height="255" alt="Screenshot 2026-04-14 184544" src="https://github.com/user-attachments/assets/2fe5f5b5-9eff-4114-a620-1f3364d28285" />
            <p>- D. On The HQ Core Switch 1 And 2 Configure IP Helper In The VLAN 172 Interface</p>
                <img width="871" height="257" alt="Screenshot 2026-04-14 184759" src="https://github.com/user-attachments/assets/6db75d16-a126-49d8-8f76-2452ae233be1" />
                <img width="868" height="322" alt="Screenshot 2026-04-14 184856" src="https://github.com/user-attachments/assets/594f4826-35be-4cac-8362-7b4855e3921a" />
            <p>- E. Configure A Switchport On HQ Access Switch 3 To Be A Member Of VLAN 172 (Guest)</p>
                <img width="870" height="349" alt="Screenshot 2026-04-14 185146" src="https://github.com/user-attachments/assets/6c1ba806-e766-4a35-abf3-fa62f624c3ff" />
            <p>- F. Install A New AccessPoint-PT And Connect It To The Newly Configure Switchport On HQ Access Switch 3</p>
                <img width="930" height="887" alt="Screenshot 2026-04-14 185514" src="https://github.com/user-attachments/assets/4869c4f1-bfe3-4efc-846e-57bb50a0620a" />
            <p>- G. Configure The New AP With A Unique SSID (GUEST), Channel, And Passphrase Using WPA2-PSK And AES</p>
                <img width="870" height="913" alt="Screenshot 2026-04-14 185635" src="https://github.com/user-attachments/assets/50978213-3eee-45bc-bf6a-9ed86fce33df" />
            <p>- H. Install A Wireless Tablet And Configure It With The Same SSID And Passphrase</p>
                <img width="935" height="891" alt="Screenshot 2026-04-14 185842" src="https://github.com/user-attachments/assets/0d840657-10ad-4e4b-9ec0-6b42f000902b" />
                <img width="873" height="878" alt="Screenshot 2026-04-14 185819" src="https://github.com/user-attachments/assets/6583ab01-a7f6-41b6-83c1-833cf46f7117" />
            <p>- I. Once The New Wireless Tablet Is Connected Confirm It Has Access To The Internet, But CANNOT Access Any Of The Corporate Networks.</p>
                <img width="873" height="1587" alt="Screenshot 2026-04-14 193747" src="https://github.com/user-attachments/assets/1cf5437a-c89c-456b-bce7-46938b665268" />
            <p><em>- Successful. This exactly what we want to see and how the guest network should behave.</em></p>
            












 





