<h1>Resource Access</h1>
<p>Resource access is the management of permissions that determine which users or systems can view, modify, or interact with specific network resources such as files, applications and devices based on user permissions and roles</p>

<h3>*Sharing a printer</h3>
<p>1. To share a printer for an organization or a branch(OU) of an organization to use, first we need to create a GPO, give it a descriptive name</p>
<p align="center"><img src="https://i.imgur.com/gNpXx1P.png" height="50%" width="50%" alt="image"/>
<p align="center"><img src="https://i.imgur.com/wmWqfjM.png" height="50%" width="50%" alt="image"/>
  
<p>2. Link the GPO to the OU by right-clicking on the OU, then click on Link an existing GPO and Select the policy created for this and click OK</p>
<p align="center"><img src="https://i.imgur.com/GsWetGy.png" height="50%" width="50%" alt="image"/>
<p align="center"><img src="https://i.imgur.com/UvYBJDb.png" height="50%" width="50%" alt="image"/>

<p>3. Next, make sure the Print Management is installed on the server.</p>
<p align="center"><img src="https://i.imgur.com/6IBbJZJ.png" height="50%" width="50%" alt="image"/>

<p><b>Note: If Print management is not installed, you can click Add roles and Features from the server manager dashboard, then select the Print and documenet service to install the print server.</b></p>
<p align="center"><img src="https://i.imgur.com/aT7xLO8.png" height="50%" width="50%" alt="image"/>

<p>4. For the purpose of the project, I downloaded the HP Universal Print Driver for WindowsPCL6(64-bit)</p>
<p align="center"><img src="https://i.imgur.com/ypB3hrs.png" height="50%" width="50%" alt="image"/>    

<p>5. Open the Print Management interface, go to Print Server>Drivers>Add Driver</p>
<p align="center"><img src="https://i.imgur.com/Uju5kFO.png" height="50%" width="50%" alt="image"/>

<p>6. On the Add Printer Driver Wizard page, click NEXT</p>
<p align="center"><img src="https://i.imgur.com/Ql7vTK9.png" height="50%" width="50%" alt="image"/>

<p>7. On the Add Printer Driver Wizard>Processor Selection page, leave it at default and click NEXT</p>
<p align="center"><img src="https://i.imgur.com/a5nn407.png" height="50%" width="50%" alt="image"/>

<p>8. On the Add Printer Driver Wizard>Printer Driver Selection page, click on Have Disk</p>
<p align="center"><img src="https://i.imgur.com/d1OoErM.png" height="50%" width="50%" alt="image"/>

<p>9. On the Install from disk page, click on Browse</p>
<p align="center"><img src="https://i.imgur.com/bP3Ig7B.png" height="50%" width="50%" alt="image"/>

<p>10. Locate the print driver file and click open</p>
<p align="center"><img src="https://i.imgur.com/8xkXEtD.png" height="50%" width="50%" alt="image"/>
<p align="center"><img src="https://i.imgur.com/pa9CpGY.png" height="50%" width="50%" alt="image"/>

<p>11. On the Add Printer Driver Wizard>Printer Driver Selection page, you can see the HP Universal Printing PCL6(v7.2.0) is listed, click NEXT.</p>
<p align="center"><img src="https://i.imgur.com/6x8Miy2.png" height="50%" width="50%" alt="image"/>

<p>12. On the Add Printer Driver Wizard>Completing the Add Printer Driver Wizard page, just click FINISH</p>
<p align="center"><img src="https://i.imgur.com/XiB0uvU.png" height="50%" width="50%" alt="image"/>

<p>13. Next, we add a printer. On the Print management interface, right-click on printer, click on Add printer</p>
<p align="center"><img src="https://i.imgur.com/vpBAqzU.png" height="50%" width="50%" alt="image"/>

<p>14. On the Network Printer Installation wizard>Printer Installation, leave it at default and click NEXT</p>
<p align="center"><img src="https://i.imgur.com/iIVYnSg.png" height="50%" width="50%" alt="image"/>

<p>15. On the Network Printer Installation wizard>Printer Address page, add an IP address, click NEXT</p>
<p align="center"><img src="https://i.imgur.com/bQzD1eX.png" height="50%" width="50%" alt="image"/>

<p>16. On the Network Printer Installation wizard>Additional port information required page, you can select the device type from the dropdown and click NEXT</p>
<p align="center"><img src="https://i.imgur.com/ZO60rRX.png" height="50%" width="50%" alt="image"/>

<p>17. On the Network Printer Installation wizard>Print Driver page, select use an existing printer driver on the computer and from the dropdown select the earlier downloaded driver and click NEXT</p>
<p align="center"><img src="https://i.imgur.com/lDYazsq.png" height="50%" width="50%" alt="image"/>

<p>18. On the Network Printer Installation wizard>Printer Name and Sharing Settings, Input a share name and click NEXT</p>
<p align="center"><img src="https://i.imgur.com/9Fzg9TJ.png" height="50%" width="50%" alt="image"/>

<p>19. On the Network Printer Installation wizard>Printer Found page, click NEXT</p>
<p align="center"><img src="https://i.imgur.com/wF5Gs3p.png" height="50%" width="50%" alt="image"/>

<p>20. On the Network Printer Installation wizard>Completing the Network Printer Installation Wizard page, click FINISH</p>
<p align="center"><img src="https://i.imgur.com/rQ9iQYP.png" height="50%" width="50%" alt="image"/>

<p>21. Back on the Print Management interface, under the Print Server, click on printers, from the list of printers, right-click on the one we just added and select Deploy with Group Policy</p>
<p align="center"><img src="https://i.imgur.com/UzDQmwq.png" height="50%" width="50%" alt="image"/>

<p>22. On the Deploy with group policy page, click browse to select the Printer Policy GPO earlier created, select “The Computers that this GPO applies to(per machine) checkbox then click Add. After this is done, click Apply and then OK.</p>
<p align="center"><img src="https://i.imgur.com/6px5OJB.png" height="50%" width="50%" alt="image"/>

<p>23. After all the steps, We need to force this update, open powershell and type in <b><i>“gpudate /force”</i></b></p>
<p align="center"><img src="https://i.imgur.com/Pr6mToq.png" height="50%" width="50%" alt="image"/>

<p>24. To confirm client computers in OU can discover this printer, go to control panel>hardware and sound>devices and printer, and there we found it. One can also go to notepad and click on print to check if the printer is part of the options</p>
<p align="center"><img src="https://i.imgur.com/1QVKxHO.png" height="50%" width="50%" alt="image"/>

<p><b>NOTE: You need to also List printer in Directory. To do this, expand Print Servers >Printer, then right-click on the printers, go to properties, enable the List in Directory checkbox, click Apply and OK</b></p>
<p align="center"><img src="https://i.imgur.com/ixqf8V5.png" height="50%" width="50%" alt="image"/>

<br>
<br>

<h3>*Configuring a Shared Folder and Accessing it by a specific Group</h3>
<p>To create a shared folder for a department and map the drive to increase work efficiencies among staff, do the following;</p>
<p>1. To create a share on the server, click on Files and storage services on the server manager</p>
<p align="center"><img src="https://i.imgur.com/h4dnFIX.png" height="50%" width="50%" alt="image"/>

<p>2. Then click on Shares, from the Shares page, click on Tasks, then New Share</p>
<p align="center"><img src="https://i.imgur.com/Ph3CHEI.png" height="50%" width="50%" alt="image"/>

<p>3. On the New Share Wizard>Select Profile for this share page, select SMB Share - Quick, then click NEXT</p>
<p align="center"><img src="https://i.imgur.com/E6DFj70.png" height="50%" width="50%" alt="image"/>

<p>4. On the New Share Wizard>Select the Server and Path for this share, make sure your server is selected and also select the drive you want to put this share on, then click NEXT</p>
<p align="center"><img src="https://i.imgur.com/KY3s8EZ.png" height="50%" width="50%" alt="image"/>

<p>5. On the New Share Wizard>Specify Share Name page, type it a descriptive share name, this will automatically create a path with the name, then click NEXT</p>
<p align="center"><img src="https://i.imgur.com/ZHmChzP.png" height="50%" width="50%" alt="image"/>

<p>6. On the New Share Wizard>Configure Share Settings page, leave it at default and click NEXT</p>
<p align="center"><img src="https://i.imgur.com/4uZEJ15.png" height="50%" width="50%" alt="image"/>

<p>7. On the Advance security settings for the share created, disable the heritable and remove all users listed except Administrators.</p>
<p align="center"><img src="https://i.imgur.com/Xuod1GS.png" height="50%" width="50%" alt="image"/>

<p>8. Then click Add, it takes you to the “Permission Entry” page, click the Principal</p>
<p align="center"><img src="https://i.imgur.com/btRxDxN.png" height="50%" width="50%" alt="image"/>

<p>9. A pop up page is opened - Select user, computer, service account or group, type the Security group or OU or user you want to add, then click check names and OK.</p>
<p align="center"><img src="https://i.imgur.com/CFRiZqn.png" height="50%" width="50%" alt="image"/>

<p>10. Back on the permission entry page, on the basic permission interface, select full control, then click OK</p>
<p align="center"><img src="https://i.imgur.com/YgnouyW.png" height="50%" width="50%" alt="image"/>

<p>11. On the Advanced Security Settings for the Share, click Apply and OK </p>
<p align="center"><img src="https://i.imgur.com/gb58r4f.png" height="50%" width="50%" alt="image"/>

<p>12. Back on the New Share Wizard>Specify Permissions to control access page, the security group is now listed, click NEXT </p>
<p align="center"><img src="https://i.imgur.com/AhsiOiv.png" height="50%" width="50%" alt="image"/>

<p>13. On the New Share Wizard>Confirm Selections page, click Create</p>
<p align="center"><img src="https://i.imgur.com/HnnNYlR.png" height="50%" width="50%" alt="image"/>

<p>14. On the New Share Wizard>View results page, click Close</p>
<p align="center"><img src="https://i.imgur.com/XkuS0mA.png" height="50%" width="50%" alt="image"/>

<p>15. Back to the Group Policy Management, right-click Group Policy Object, then New</p>
<p align="center"><img src="https://i.imgur.com/IpAWsZu.png" height="50%" width="50%" alt="image"/>

<p>16. Put in a descriptive name, then click OK</p>
<p align="center"><img src="https://i.imgur.com/zvh0H6R.png" height="50%" width="50%" alt="image"/>

<p>17. On the Group Policy Management>Group Policy Object, right-click on the policy and go to edit</p>
<p align="center"><img src="https://i.imgur.com/mMBibFu.png" height="50%" width="50%" alt="image"/>

<p>18. On the Group Policy Management Editor, go to this path <b><i>User configuration>Preferences>Windows Settings>Drive Maps>New>Mapped Drive</i></b> and this opens up the New drive properties</p>
<p align="center"><img src="https://i.imgur.com/8zNyEAy.png" height="50%" width="50%" alt="image"/>

<p>19. On the New drive properties>general tab, leave the action, add the network location of the drive, put in a label as  to describe the drive, then select a drive letter. </p>
<p align="center"><img src="https://i.imgur.com/DMP2MQl.png" height="50%" width="50%" alt="image"/>

<p>20. On the New drive properties>Common tab, select Item-level targeting</p>
<p align="center"><img src="https://i.imgur.com/oz5jLTr.png" height="50%" width="50%" alt="image"/>

<p>21. On the targeting editor page, go through the dropdown and select security group</p>
<p align="center"><img src="https://i.imgur.com/qshWfcQ.png" height="50%" width="50%" alt="image"/>

<p>22. This opens up the group box, click to browse</p>
<p align="center"><img src="https://i.imgur.com/Xf1RBDt.png" height="50%" width="50%" alt="image"/>

<p>23. On the Select group page, type the security group, click check names and then click OK</p>
<p align="center"><img src="https://i.imgur.com/3qTKhTy.png" height="50%" width="50%" alt="image"/>

<p>24. Back to the targeting editor page, the security group is now listed, click OK</p>
<p align="center"><img src="https://i.imgur.com/xMKeLFd.png" height="50%" width="50%" alt="image"/>

<p>25. Back to the Drive properties’ page, click Apply and OK</p>
<p align="center"><img src="https://i.imgur.com/pGIWXB0.png" height="50%" width="50%" alt="image"/>

<p>26. Now to link this policy to an OU, back on the group policy management page, right-click on the OU and click on Link an existing GPO</p>
<p align="center"><img src="https://i.imgur.com/EYBfbi9.png" height="50%" width="50%" alt="image"/>

<p>27. On the Select GPO page, click on the policy then click OK</p>
<p align="center"><img src="https://i.imgur.com/uDdFBlz.png" height="50%" width="50%" alt="image"/>

<p>28. 28.To confirm, log in to one of the computers in that OU and go to file explorer, the drive will be there. </p>
<p><b>Note - It might be required for you to restart the computer in the OU first.</b></p>
<p align="center"><img src="https://i.imgur.com/xDTPL5u.png" height="50%" width="50%" alt="image"/>

<br>
