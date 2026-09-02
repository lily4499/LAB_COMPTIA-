Yes. Here is the full click-by-click process shown for the 7.3.3 Fix a Network Connection lab. The lab has two problems: the Ethernet cable is disconnected, and the workstation needs manual IPv4 settings because there is no DHCP server. ([Fignberry][1])

### Part 1 — Confirm the network problem

1. Click Keep Working if the Score Lab window is open.
2. On the Windows desktop, go to the network icon near the clock.
3. Right-click the network icon.
4. Select Network & Internet settings.
5. Notice that the computer does not have internet access.
6. Select Advanced network settings.
7. Find More network adapter options under Related settings.
8. Open it.
9. Look at the Ethernet adapter.
10. It should show something like:

```text
Network cable unplugged
```

11. Close the Network Connections window.
12. Close Settings. ([Fignberry][1])

### Part 2 — Fix the Ethernet cable

1. At the upper-left of the lab, click Office 1.
2. You should now see the physical computer.
3. Above the computer, click Back.
4. Look at the Ethernet connection on the back of the computer.
5. Notice that the link light is not active.
6. Click the network/Ethernet cable.
7. Look at the Selected Component pane.
8. You should see that one side of the cable is already connected to the PC but the other side is disconnected.
9. Select the loose end of the cable.
10. Drag that end to the Ethernet/network jack on the wall plate.

You now have:

```text
Office1 PC
    │
 Ethernet cable
    │
Wall network jack
```

The physical connection is fixed. ([Fignberry][1])

### Part 3 — Return to Windows

1. Click the monitor.
2. Select Click to view Windows 11.
3. Look at the network icon.

You should now see that the physical Ethernet connection exists.

But you are not finished because this network does not use DHCP. You need to configure the IP address manually. ([Quizlet][2])

### Part 4 — Configure the static IPv4 settings

1. Right-click the Start button.
2. Select Settings.
3. Select Network & internet.
4. Select Ethernet.
5. Find IP assignment.
6. Click Edit.
7. Change the setting from Automatic/DHCP to:

```text
Manual
```

8. Turn IPv4 On.
9. Enter:

```text
IP address:       192.168.0.27
Subnet mask:      255.255.255.0
Gateway:          192.168.0.5
Preferred DNS:    163.128.78.93
```

You can also use `163.128.80.93` as the preferred DNS server according to the walkthrough. ([Fignberry][1])

Why `192.168.0.27`?

The lab tells you:

```text
Below .15     = servers
.30 through .34 = other workstations
```

So `.27` is available and valid. ([Quizlet][2])

10. Click Save.
11. Close Settings.

Your Office1 configuration should now look like:

```text
Office1
IP:      192.168.0.27
Mask:    255.255.255.0
Gateway: 192.168.0.5
DNS:     163.128.78.93
```

### Part 5 — Test the connection

1. Right-click Start.
2. Select Windows Terminal or Terminal.
3. At the PowerShell prompt, type:

```powershell
ping 163.128.78.93
```

4. Press Enter.

You want to see replies similar to:

```text
Reply from 163.128.78.93
Reply from 163.128.78.93
Reply from 163.128.78.93
Reply from 163.128.78.93
```

That confirms Office1 can reach the DNS server. ([Fignberry][1])

The lab instructions also say Office1 should ultimately be able to communicate with both Office2 and the DNS server. ([Quizlet][2])

You can therefore also test:

```powershell
ping Office2
```

or use Office2's IP address from Exhibits.

### Part 6 — Finish the lab

Once the connection works:

1. Close Terminal.
2. Click Check Answers or Score Lab.
3. The required actions should show as completed:

```text
✓ Plug the workstation into the network
✓ Configure TCP/IP settings
```

The important troubleshooting order in this lab is:

```text
No network
   ↓
Check physical connection
   ↓
Connect Ethernet cable
   ↓
Configure static IPv4
   ↓
Ping DNS / Office2
   ↓
Score Lab
```

This is also a good CompTIA pattern to remember: physical connection first → IP configuration second → connectivity test last.

[1]: https://www.fignberry.club/pages/module_4/7.3.3_Lab_Fix_A_Network_Connection?utm_source=chatgpt.com "7.3.3 Lab: Fix A Network Connection"
[2]: https://quizlet.com/965697606/cit-111-1194-lab-fix-a-network-connection-1-flash-cards//?utm_source=chatgpt.com "Fix Network Connections - Cit 111 Lab 11.9.4 Guide Flashcards | Quizlet"
