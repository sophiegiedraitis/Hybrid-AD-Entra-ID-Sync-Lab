# Hybrid-AD-Entra-ID-Sync-Lab

<img width="472" height="205" alt="Screenshot 2026-10-11 170451" src="https://github.com/user-attachments/assets/3031ffab-cc78-484a-8079-ec8d9b9560bf" />


<p align="center">
<img 
</p>

 
 <h3>
  
 </h3>

<h2>
 Skills Demonstrated
</h2>
 
- Microsoft Entra
- VMWare
- Microsoft Azure AD Connect
- Microsoft Active Directory


<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Microsoft Sentinel
- Log Analytics Workspace
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 11 Pro (Virtual Machine)</b> (version 22H2)                                                               

<h2>List of Prerequisites</h2>

- Microsoft Azure tenant
- Remote Desktop                                                                 


<h2>Installation Steps</h2>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Microsoft Sentinel
- Log Analytics Workspace
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 11 Pro (Virtual Machine)</b> (version 22H2)                                                               

<h2>List of Prerequisites</h2>

- Microsoft Azure tenant
- Remote Desktop
- Powershell

<h2>Installation Steps</h2>

 <p>
1. For this lab we are creating a DC1 server to act as our on-premise domain server and a computer called Sync1. We are going to domain join the Sync1 computer to the DC1 computer. We are going to install Azure AD Connect onto the Sync1 server instead of DC1 in-order to decrease the load we are putting onto the main server and to establish difference functions between DC1 and Sync1.

<img width="855" height="447" alt="Screenshot 2026-10-11 170206" src="https://github.com/user-attachments/assets/8d9d7c24-0ed4-4e50-bdf7-419ce06c2402" />
<img width="1345" height="672" alt="image (10)" src="https://github.com/user-attachments/assets/bfc6f6b2-c88c-4290-8fe0-757941214dea" />

                                                                                                                        
                                                                                                                        
<p>
Once the DC1 server is created in VMware we will need to promote the server to a AD domain server. Within the server go to Manage < Add Roles and Features < AD Domain and Users  < Once that is created you go to promote to domain controller. We are going to add in a new forest and put in the domain that we are assigning to the server
</p> 
<img width="791" height="587" alt="Screenshot 2026-10-11 172202" src="https://github.com/user-attachments/assets/b649163e-fc09-49e1-b12b-c1fc32c3778a" />
<img width="857" height="632" alt="Screenshot 2026-10-11 172359" src="https://github.com/user-attachments/assets/2186a1fa-a807-4d58-b1d9-3c21ade97cb9" />

                                                                                                                        
3. <p>
 Now we will go ahead and add-in the UPN domain on our Entra tenant to our list of domain choices in ADUC.
</p>

<img width="875" height="511" alt="Screenshot 2026-10-11 172957" src="https://github.com/user-attachments/assets/f8340113-676f-4bea-9ed7-772ae9e28b62" />

4. <p>
Now we can go and set the static IP of DC!. This will allow Sync1 to be able to find and communicate with DC1. 
</p>
<img width="872" height="776" alt="static_ip" src="https://github.com/user-attachments/assets/be8a3cf0-79d6-4845-96b3-a7a60a16b6d6" />

5. <p>
Once the DC1 Server and Sync1 Server are setup, you want to configure the Sync1 sever to connect to the DC1 Server. Change the DNS of Sync1 to to be the IP address of DC1
</p>

<img width="872" height="776" alt="static_ip" src="https://github.com/user-attachments/assets/1090ca89-6394-4260-8652-5cd81dd7e698" />

6. <p>
 Then after changing it in Sync1 go and do
ipconfig /flushdns

ipconfig/all

Then you want to enable ping ipv4 from each server

windows+R: wf.msc

Scroll down to file and print sharing rules and enable that for Ipv4 and have the servers ping each other to test out the connection
</p>



