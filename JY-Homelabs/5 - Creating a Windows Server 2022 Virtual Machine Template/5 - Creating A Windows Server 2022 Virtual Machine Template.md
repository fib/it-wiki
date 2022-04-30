Summary

1.  Select a hyper-visor of your choice. ESXi… Hyper-V…VMWare
    Workstation… anything!

2.  Create Virtual Machine and name it **WIN2022_TEMPLATE**

3.  Install Windows Server 2022 (Follow lab 4)

4.  Login when the installation is complete

Process:

1.  Follow lab 4 to create and install a new Windows Server 2022 virtual
    machine. However, name the virtual machine **WIN2022_TEMPLATE  
    **

2.  When lab 4 is completed, the first thing you will do is install
    VMWare tools. To do this, log into vCenter Server and right-click on
    the Virtual Machine. Hover over **Guest OS** and then a secondary
    menu will appear. Click on **Install VMWare Tools…** (for those
    using a different hypervisor this process is relatively the same.
    Install the Guest OS tools for the hyer-visor that you are using.
    Hyper-V calls this *Guest Services*, VMware’s version is called
    *VMWare Tools*).  
      
    <img src="./media/image1.png" style="width:5.50467in;height:2.8in" />  
      
    When the window appears.. click on **Mount**.

3.  After clicking on Install VMWare tools, log into your virtual
    machine and open up the file explorer. There should be a **DVD
    Drive** now appearing called **DVD Drive (D) VMWare Tools**.
    Double-click this “DVD” drive.  
      
    <img src="./media/image2.png" style="width:6.5in;height:1.27153in"
    alt="Graphical user interface, text, application Description automatically generated" />

4.  The installation should begin immediately and a VMWare Tools Setup
    install wizard should appear. Click **Next** all the way through,
    keeping everything default.  
      
    <img src="./media/image3.png" style="width:3.49441in;height:2.75875in"
    alt="Graphical user interface, application, Word Description automatically generated" />

5.  When the Installer has finished, it will ask if you wish to restart
    to have the changes take affect. Click **YES** on this window.  
      
    <img src="./media/image4.png" style="width:3.37925in;height:1.60997in"
    alt="Graphical user interface, text, application Description automatically generated" />

6.  When your virtual machine comes back online, you should now get a
    better console window that resizes to fit to your screen. If not,
    close and re-open the console window from vCenter Server, it should
    re-adjust. Please keep in mind that, if VMWare tools ever gets
    updated, you should always run this installer again on the virtual
    machine template. Same with Windows Updates.

7.  Log back into your server, and close the Server Manager if it
    automatically opens.

8.  Open the File Explorer and go to your C: drive, and make a new
    folder called **Sysadmin Tools**.  
      
    <img src="./media/image5.png" style="width:2.86458in;height:2.14583in"
    alt="Graphical user interface, application Description automatically generated with medium confidence" />

9.  Navigate into the **SysadminTools** folder.

10. Open Microsoft Edge in your virtual machine and navigate to
    <https://docs.microsoft.com/en-us/sysinternals/downloads/>

11. Scroll down until you see **Bginfo** and click on it’s hyperlink  
      
    <img src="./media/image6.png" style="width:6.5in;height:0.93681in"
    alt="Text Description automatically generated with medium confidence" />

12. On the next page, click **Download BgInfo**  
      
    <img src="./media/image7.png" style="width:3.51349in;height:2.82607in"
    alt="Graphical user interface, text, application, chat or text message Description automatically generated" />

13. This will download a file to your Downloads folder. Navigate to your
    Downloads folder, and move it to C:\SysadminTools

14. Once **BgInfo** is in the C:\SysadminTools directory, right click
    **Bginfo.zip** and click **Extract All**.

15. Click **Extract** when the window opens. It should extract to
    **C:\SysadminTools\BGInfo  
      
    **<img src="./media/image8.png" style="width:4.05536in;height:2.86776in"
    alt="Graphical user interface, text, application, email Description automatically generated" />**  
      
    **

16. Close the new Windows Explorer window that opens. Do not do anything
    else with BGInfo, this is just to place it here ahead of time so
    that when you do deploy a new VM template, it is easily accessible
    and ready to install.

17. Close all other Windows Explorer windows.

18. Next, at the bottom left hand corner of the screen, click the Start
    Button and then **Right click** on Windows Powershell, hover over
    **More** and then click on **Run As Administrator**.  
      
    <img src="./media/image9.png" style="width:6.5in;height:2.53472in"
    alt="Graphical user interface, application Description automatically generated" />

19. A new Powershell window should now be open. In this window, type the
    following command: **Set-ExecutePolicy -ExecutionPolicy ByPass** and
    then hit Enter.

20. A warning will appear, type **A** to select *Yes to All* and then
    hit ENTER again.  
      
    <img src="./media/image10.png" style="width:6.5in;height:3.42708in"
    alt="Text Description automatically generated" />

21. The command should complete with no output.

22. Close the Powershell Window.

23. Next you will click the **Start Button**, then click on
    **Settings**.  
      
    <img src="./media/image11.png" style="width:2.46935in;height:2.50648in"
    alt="Graphical user interface, application Description automatically generated" />

24. The Windows Settings will open, click on **Update & Security  
      
    **<img src="./media/image12.png" style="width:2.89583in;height:1in"
    alt="Text Description automatically generated with medium confidence" />**  
    **

25. This will open the *Windows Update* section. Click on **Check For
    Updates**.  
      
    <img src="./media/image13.png" style="width:4.31733in;height:1.67592in"
    alt="Graphical user interface, text, application, email Description automatically generated" />

26. It should begin downloading and installing the latest updates
    automatically. Depending on your hardware, CPU, RAM, Local Area
    Network and Internet Service Provider, this can take time. Allow
    this to run… go grab some coffee.  
      
    <img src="./media/image14.png" style="width:5.50082in;height:3.16297in"
    alt="Graphical user interface, text, application, email Description automatically generated" />

27. Allow all the updates to finish installing. Skip the optional
    quality updates as those are typically previews. If your virtual
    machine requires a reboot to commit an update, please do so now. To
    check and see if a Windows Server is pending a reboot, click on
    **View Update History**.  
      
    <img src="./media/image15.png" style="width:3.04167in;height:0.64583in"
    alt="Text Description automatically generated with medium confidence" />

28. This page will list whether an update is installed or **pending a
    reboot**, since we recently downloaded the Windows Server 2022
    Evaluation ISO, I did not have any new Cumulative updates for the
    Operating System. These Cumulative updates include <u>security</u>
    updates for the operating system that should be installed monthly.  
      
    <img src="./media/image16.png" style="width:6.5in;height:4.26667in"
    alt="Graphical user interface, text, application, email Description automatically generated" />

29. The final step we will perform in the operating system is enable
    remote desktop connections to be allowed to remotely connect to the
    Windows Server. To do this, go back to the **Windows Settings**
    page. (Start Button -\> Settings Cogwheel)

30. At the top of the Windows Settings page, you will see *Find A
    Setting* with a text box. Type **Remote Desktop** in that text box.
    Results should preview below the textbox as you begin typing, click
    on **Allow remote connections to this computer**.  
      
    <img src="./media/image17.png" style="width:3.75in;height:2.36458in"
    alt="Graphical user interface, text, application, email Description automatically generated" />

31. Scroll down until you see **Remote Desktop** as a heading. There
    will be a blue checkbox showing *Change settings to allow remote
    connections to this computer*. Click on **Show Settings**.  
      
    <img src="./media/image18.png" style="width:5.16667in;height:1.73958in"
    alt="A screenshot of a computer Description automatically generated with medium confidence" />

32. A dialog box will appear, within the **Remote Desktop** section of
    this dialog box, click the radio button that says **Allow remote
    connections to this computer**. This will prompt a warning window
    stating that you are opening up the remote desktop protocol for all
    network types… just click **Ok** for now.  
      
    <img src="./media/image19.png" style="width:3.12417in;height:3.60841in"
    alt="Graphical user interface, text, application, email Description automatically generated" />

33. Click **Apply** and then **OK**.

34. Close the **Windows Settings** window.

35. If you know how to use RDP/Remote Desktop Protocol, you may test it
    at this time to make sure you can connect. At this time, you may now
    gracefully shut down the virtual machine as we will convert this
    virtual machine into a template next.  
      
    <img src="./media/image20.png" style="width:2.82549in;height:1.66734in"
    alt="Graphical user interface, text, application Description automatically generated" />

36. Once the Virtual Machine is completely shut down, log into the
    vCenter Server / vSphere Console.

37. Optional: Click on the **WINDOWS2022_TEMPLATE** virtual machine you
    just shut down and you may modify the **CPU** and **RAM** only. Set
    it to your personal preference. If there is no preference, keep it
    at **2 CPU** and **4GB of RAM** as those are the bare minimum
    requirements for Windows Server 2022 (Desktop Experience). <u>Make
    sure to disconnect the DVD/CD Drive Windows Installation
    Media!!!</u>

38. Right-Click on **WIN2022_TEMPLATE**, click on **Template** and then
    click on **Convert To Template**.  
      
    <img src="./media/image21.png" style="width:6.5in;height:1.32778in"
    alt="Graphical user interface, text, application Description automatically generated" />

39. When the warning window appears, click **Yes**, stating that you
    wish to convert the virtual machine **WIN2022_TEMPLATE** to a
    template.  
      
    <img src="./media/image22.png" style="width:5.97917in;height:2.17708in"
    alt="Graphical user interface, text Description automatically generated" />

40. The virtual machine should now disappear from your virtual machine
    inventory.

41. If you click on the “file” looking icon at the top left of the
    vSphere console, you will see a folder structure. It should be
    sitting under the **Templates** directory now.  
      
    <img src="./media/image23.png" style="width:4.02083in;height:2.92708in"
    alt="Graphical user interface, text, application Description automatically generated" />

42. Ok… so great. Now how do we use it? Great question.

43. Right-Click on your Cluster or Host and create a new virtual
    machine.  
      
    <img src="./media/image24.png" style="width:3.92708in;height:1.33333in"
    alt="Graphical user interface, application Description automatically generated" />

44. This time… you want to select **Deploy From Template** and then
    click next.  
      
    <img src="./media/image25.png" style="width:6.5in;height:2.94931in"
    alt="Graphical user interface, text, application, chat or text message Description automatically generated" />

45. Now you can select it from your Content Library or Data Center hosts
    (VMWare). Your experience may vary in other hyper-visors such as
    Oracle VirtualBox. Select the template you just created,
    **WIN2022_TEMPLATE** and click next.  
      
    <img src="./media/image26.png" style="width:5.89583in;height:3.05208in"
    alt="Graphical user interface, application Description automatically generated" />

46. Then… configure your virtual machine as you normally would. Give it
    any name you want. In VMWare it will give you some clone options, I
    don’t select any and click next until the wizard is finished.

47. Your hypervisor will now clone from the template and create the new
    virtual machine.

48. **Make sure to not forget to disconnect the Windows Installation
    media from the Virtual Machine, I forgot to include this earlier in
    the process before converting the template into a Virtual Machine.
    Always check and make sure just in case you forgot when making the
    template.  
      
    **<img src="./media/image27.png" style="width:6.5in;height:2.99792in"
    alt="A screenshot of a computer Description automatically generated" />**  
    **

49. Power on your virtual machine!

50. Open the console and it should lead you straight to the CTRL+ALT+DEL
    screen, go ahead and log in.

51. Once you are logged in the **Server Manager** window will open, this
    time don’t close it!

52. Click on **Local Server** in the Server Manager.  
    **  
    **<img src="./media/image28.png" style="width:2.25in;height:1.4375in"
    alt="Graphical user interface Description automatically generated with medium confidence" />**  
    **

**  
**

53. The very first field you should see on the left side is **Computer
    Name**, go ahead and change that to whatever name you gave the
    virtual machine. Now is also the time to join the domain if you have
    one present. If you don’t, then just change the computer name.

54. To change the Computer name, click on the actual name.  
      
    <img src="./media/image29.png" style="width:3.39583in;height:0.91667in"
    alt="A picture containing text Description automatically generated" />

55. This will open a new dialog window. Click on **Change**.  
    **  
    **<img src="./media/image30.png" style="width:4.22917in;height:3.27083in"
    alt="Graphical user interface, text, application, email Description automatically generated" />**  
      
    **

**  
**

56. Another dialog window will open, go ahead and change the **Computer
    Name** (and optionally the domain you wish to join as well), then
    click **Ok**. After you click Ok, it will think for a minute…. Then
    a dialog box will appear stating that you need to reboot your
    machine. Click **Ok**.  
      
    <img src="./media/image31.png" style="width:3.27083in;height:4.09375in"
    alt="Graphical user interface, text, application, email Description automatically generated" />  
    **  
    **<img src="./media/image32.png" style="width:3.54167in;height:1.80208in"
    alt="Graphical user interface, text, application Description automatically generated" />**  
    **

**  
**

57. After you click ok the dialog boxes will close. Close the **System
    Properties** dialog box as well, along with Server Manager.

58. Reboot your Virtual Machine to apply the name change.  
      
    <img src="./media/image33.png" style="width:3.65625in;height:1.75in"
    alt="Graphical user interface, text, application, email Description automatically generated" />

59. When the virtual machine comes back online, log back in and open
    **Powershell**.

60. In Powershell, type **hostname** and press enter. It should now
    reflect the name you just changed the Windows virtual machine to.  
      
    <img src="./media/image34.png" style="width:3.11458in;height:0.67708in"
    alt="A screenshot of a computer Description automatically generated with medium confidence" />

61. Close Powershell and open Windows Explorer. Navigate to
    **C:\Sysadmintools\BGinfo**

62. Double click on **Bginfo64  
      
    **<img src="./media/image35.png" style="width:4.30208in;height:1.51042in"
    alt="Table Description automatically generated" />**  
    **

**  
**

63. Click on Agree for the License Agreement  
      
    <img src="./media/image36.png" style="width:3.84528in;height:2.59618in"
    alt="Graphical user interface, text, application, email Description automatically generated" />

64. The application should install and immediately open, click on
    **Apply** and then **OK**.  
      
    <img src="./media/image37.png" style="width:3.81914in;height:3.29066in"
    alt="Graphical user interface, text Description automatically generated" />

65. Now minimize your window and look at your desktop. You will notice
    some information populating over your Desktop image background.

**  
**

66. If you change your desktop background just to be black, it makes it
    easier to read. This is how we have it set up at my work.  
      
    <img src="./media/image38.png" style="width:6.35417in;height:5.42708in"
    alt="Text Description automatically generated" />

67. You are complete!

68. Key Takeaways:

    1.  Don’t forget to disconnect the Windows Installation Media when
        converting a Virtual Machine to a template.

    2.  You can install other programs such as Google Chrome, Firefox,
        Office products etc, as many as you’d like when making a
        template.

    3.  I for the most part followed Microsoft’s guide which is located
        here:
        <https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/manage/hybrid/server/best-practices/vmware-windows-template>
