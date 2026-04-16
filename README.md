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
        <p>- G. Configure Private WAN Border Gateway Protocol (BGP) Peering</p>
            <p>- I. BGP ASN 65123</p>
                <p>- 1. Router ID</p>
                <p>- 2. Neighbor</p>
                <p>- 3. Networks</p>
        <p>- H. Configure Default Route Pointing To Private WAN Neighbor IP</p>
        <p>- I. Configure Private WAN Voice Quality Of Service</p>
            <p>- I. VOIP Control And RTP Access-Lists</p>
            <p>- II. VOIP Control And RTP Class-Maps</p>
            <p>- III. Policy-Map</p>
            <p>- IV. Apply Policy-Map To Private WAN Interface G0/</p>
        <p>- J. Configure Telephony-Service</p>
            <p>- I. Max-Ephones</p>
            <p>- II. Max-DN</p>
            <p>- III. IP Source-Address</p>
        <p>- K. Configure Branch 1 Ephone-DNS</p>
            <p>- x2001, x2002</p>
        <p>- L. Configure PSTN Access-List</p>
        <p>- M. Configure PSTN Voice Interface G0/1</p>
            <p>- I. IP Address</p>
            <p>- II. Disable CDP</p>
            <p>- III. Apply PSTN Access-List Inbound</p>
        <p>- N. Configure Internal Dial-Peers</p>
            <p>- I. HQ Extensions (1…$)</p>
        <p>- O. Configure Outbound Dial-Peers</p>
            <p>- I. 10-Digit Long Distance And Toll-Free</p>
            <p>- II. 7-Digit Local</p>
            <p>- III. International </p>
            <p>- IV. 411 & 911</p>
        <p>- P. Configure Outbound Translation Rules <em>(Lab Configuration Not Supported)</em></p>
        <p>- Q. Configure Inbound Dial-Peers <em>(Lab Configuration Not Supported)</em></p>
        <p>- R. Configure Inbound Voice Translation Rules <em>(Lab Configuration Not Supported)</em></p>
        <p>- S. Configure Voice Service VoIP <em>(Lab Configuration Not Supported)</em></p>
        <p>- T. Configure Session Initiation Protocol (SIP) <em>(Lab Configuration Not Supported)</em></p>
        <p>- U. Configure DSP Services <em>(Lab Configuration Not Supported)</em></p>
    <p><b>Step 2: Install and Configure The Branch 1 Switch</b></p>
        <p>- A. Rack, Mount, And Power On All Three Switches</p>
        <p>- B. Basic Router Configurations (Hostname, NTP, Domain-Name, SSH, Etc)</p>
        <p>- C. Configure VLAN Trunking Protocol (VTP) Transparent</p>
        <p>- D. Configure MGMT VLAN Interface</p>
        <p>- E. Configure Default Gateway</p>
        <p>- F. Configure And Connect Trunks Port Back To The Branch 1 Router</p>
        <p>- G. Configure Access Ports</p>
        <h2><strong><u>Implementation</u></strong></h2>
        <h3>Step 1: Install And Configure The Branch 1 Router</h3>
            <p>- A. Install An AccessPoint-PT And Connect It To HQ Core Switch 2 Into An Access Port.</p>
            <p>- First, we will rack, mount, and power on the cisco 2911 router.</p>
                <img width="1395" height="873" alt="Screenshot 2026-04-16 161350" src="https://github.com/user-attachments/assets/721ece10-de94-4c77-92cd-9dfc35198b4b" />
            <p>- B. Next, we will install the uck9 license.</p>
                <img width="866" height="995" alt="Screenshot 2026-04-16 161731" src="https://github.com/user-attachments/assets/7afcbaa1-7742-4097-b7c1-fc429f8569d0" />
                <img width="870" height="1137" alt="Screenshot 2026-04-16 161850" src="https://github.com/user-attachments/assets/52ae8506-d271-499e-9370-496677da66cd" />
                <img width="871" height="1354" alt="Screenshot 2026-04-16 161944" src="https://github.com/user-attachments/assets/377ce501-7d58-4aba-9849-8ea7e602f504" />
                <img width="872" height="1217" alt="Screenshot 2026-04-16 162032" src="https://github.com/user-attachments/assets/b597394e-aaee-4a8e-beaf-6bd237de2906" />
            <p>- C. Next we will do basic Router configurations (hostname, NTP, domain-name, SSH, etc).</p>
                <img width="874" height="968" alt="Screenshot 2026-04-16 162754" src="https://github.com/user-attachments/assets/3e343fe9-285e-4a55-89e8-875eee416989" />
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
                <img width="869" height="887" alt="Screenshot 2026-04-16 163432" src="https://github.com/user-attachments/assets/c0710a87-16ea-4e29-9e90-a407b5486548" />
            <p>- E. Next, we'll configure DHCP services for branch 1 data and voice networks.</p>
                1. First, address exclusions for the DCHP pools.
                <img width="870" height="225" alt="Screenshot 2026-04-16 163950" src="https://github.com/user-attachments/assets/381602d7-4f18-4d78-a47e-eadc7ed229d4" />
                2. Second, we'll configure the DHCP pool for B1-data (network, default-router, dns server, etc.)
                <img width="867" height="283" alt="Screenshot 2026-04-16 164226" src="https://github.com/user-attachments/assets/6851ab5c-dd2f-40e4-922d-bf4f6e977239" />
                3. Lastly, we'll configure the DHCP pool for B1-voice.
                <img width="873" height="283" alt="Screenshot 2026-04-16 164428" src="https://github.com/user-attachments/assets/e05789f3-d520-48ec-9db4-80887c200932" />
                <p><em>- The option "150 command" adds the TFTP option. Also no DNS server is required to be handed out to the phones on the network.</em></p>
            <p>- F. For this next step, and also the next series of steps we will now configure and connect private WAN interface G0/1.</p>
                <img width="865" height="403" alt="Screenshot 2026-04-16 164854" src="https://github.com/user-attachments/assets/cf723a89-e356-4125-ba15-e78ee110d140" />
                <img width="1208" height="865" alt="Screenshot 2026-04-16 164959" src="https://github.com/user-attachments/assets/baf55426-a5e2-4134-b95d-0d47afda7e19" />
                <img width="873" height="334" alt="Screenshot 2026-04-16 165109" src="https://github.com/user-attachments/assets/899d97c2-5cc9-42a4-a866-4b97ea88ddf3" />
                <p><em>- And as you can see, we have successful pings to the provider router. As a side note, we also configured "no cdp enable" to ensure we aren't sending cdp hello messages to the provider network.</em></p>
            <p>- G. Next, we'll configure private WAN border gateway protocol (BGP) peering.</p>
                1. We'll start by configuring the BGP router ID and set up peering with the provider router.
                <img width="869" height="243" alt="Screenshot 2026-04-16 165712" src="https://github.com/user-attachments/assets/9d88ca45-7162-4080-8041-9427d952251f" />
                <p><em>- Command "router bgp 65123" starts so we can enter the configuration for autonomous system #65123. Command "bgp router-id 192.168.250.6" forces the router to us g0/1 IP as the BGP ID. Command "neighbor 192.168.250.5 remote-as 65535" configures the BGP peer.</em></p>
                2. Second, we'll configure network statements to advertise across the private WAN.
                <img width="870" height="1094" alt="Screenshot 2026-04-16 170216" src="https://github.com/user-attachments/assets/4cbe6e60-4d19-45a2-b592-172574edbecb" />
                <p><em>- "network 192.168.120.0 mask 255.255.255.0" advertises B1 MGMT, "network 192.168.20.0 mask 255.255.255.0" advertises B1 DATA, "network 10.10.20.0 mask 255.255.255.0" advertises B1 VOICE.</em></p>
                <p><em>- Let's check the bgp neighbor to make sure it is connected:</em></p>
                <img width="874" height="365" alt="Screenshot 2026-04-16 170610" src="https://github.com/user-attachments/assets/cbf3841e-e22b-4c9d-a4e0-4635d7496897" />
                <img width="871" height="1559" alt="Screenshot 2026-04-16 170656" src="https://github.com/user-attachments/assets/2056a6eb-5e06-43a6-a93c-307944b0e2d5" />
                <img width="871" height="745" alt="Screenshot 2026-04-16 170810" src="https://github.com/user-attachments/assets/cbc721c6-7581-4317-a631-97c784cbf119" />
                <img width="870" height="680" alt="Screenshot 2026-04-16 170928" src="https://github.com/user-attachments/assets/8b0611ec-527b-48e4-a5d5-ba86e494fd38" />
                <p><em>- Successful.</em></p>


                


                
                

                
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            <p>- D. Now, we'll configure and connect branch 1 LAN interface G0/0. We'll set our VLANS respectively as well. (Mgmt interface vlan 100, data interface vlan 192, voice interface vlan 10.)</p>
            
        <h3>Step 2: Install and Configure The Branch 1 Switch</h3>
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
            












 





