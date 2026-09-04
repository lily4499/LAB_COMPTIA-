For **Lab 133.6.2.7 – Configure IP Addresses**, you can explain it in an interview like a small networking project.

> One networking project I completed involved manually configuring IPv4 settings on a Windows workstation with two network adapters. The workstation needed to connect to the company’s main network and also to a separate internal network.
>
> I first reviewed the network diagram to identify the correct subnet, gateway, and DNS information. For the main Ethernet adapter, I assigned a static IP address of `192.168.0.254` with a `255.255.255.0` subnet mask. I configured the default gateway as `192.168.0.5` and added the preferred and alternate DNS servers provided in the network diagram.
>
> For the second network adapter, I configured `10.0.255.254` with a `255.255.0.0` subnet mask. Because that adapter was only for a local internal network, I left the gateway and DNS fields blank.
>
> After configuring both adapters, I verified the settings and tested connectivity by pinging the preferred DNS server. The ping returned successfully with no packet loss, which confirmed that the workstation could communicate through the network correctly.
>
> This project gave me hands-on practice with static IPv4 configuration, subnet masks, default gateways, DNS, multiple network adapters, and connectivity testing in Windows.

A shorter interview version would be:

> I completed a Windows networking lab where I configured static IPv4 settings on a workstation with two NICs. I used the network diagram to determine the correct IP addresses, subnet masks, gateway, and DNS settings. I configured the main adapter for company and Internet access, configured the second adapter for an internal network, and then verified connectivity using `ping`. The test completed successfully with 0% packet loss.

A very simple way to remember the project is:

**Situation:** A company workstation needed to connect to two different networks.

**Task:** Manually configure both network adapters.

**Action:** Set the IP address, subnet mask, gateway, and DNS where required.

**Result:** Verified successful communication by pinging the DNS server.

If the interviewer asks, **“What did you learn from that project?”**, you can say:

> I learned how the IP address identifies the computer, the subnet mask defines the local network, the default gateway allows communication outside the local network, and DNS helps systems reach resources by name. I also learned how to verify a configuration instead of assuming it works.


---

---

The **situation** in this lab was that you were acting as the **IT administrator for a small company**.

A workstation in the **executive office** needed to connect to **two different networks**:

* the company’s normal network, which also gives access to the internet
* a second small private network that was not fully built yet

The computer had **two network cards**:

* **Ethernet**
* **Ethernet 2**

Because the computer had to communicate correctly on both networks, you needed to manually configure the IPv4 settings for each card.

A simple way to think about it is:

> The executive computer had two doors. One door went to the company network and internet, and the second door went to a small private network. You had to give each door the correct network address.

For **Ethernet**, you configured the company-network connection:

```text
IP address:       192.168.0.254
Subnet mask:      255.255.255.0
Default gateway:  192.168.0.5
Preferred DNS:    163.128.80.93
Alternate DNS:    163.128.78.93
```

This connection needed a **gateway and DNS** because it had to reach other networks and the internet.

For **Ethernet 2**, you configured the small private network:

```text
IP address:       10.0.255.254
Subnet mask:      255.255.0.0
Gateway:          blank
DNS:              blank
```

This connection did not need a gateway or DNS because it was only for that local private network.

After configuring both cards, you tested the main Ethernet connection by running:

```powershell
ping 163.128.80.93
```

You received replies, which proved the computer could successfully communicate with the preferred DNS server.

So the whole lab was basically:

**Situation:** An executive computer needed access to two networks.

**Problem:** The network cards did not yet have the correct manual IP settings.

**What you did:** You configured the IP address, subnet mask, gateway, and DNS information.

**How you verified it:** You used `ping` to make sure the connection worked.

A good CompTIA-style summary to remember is:

> **Configure → Verify → Test**

You configured the IP settings, verified them, and tested connectivity with `ping`.


---
-----

This lab was about **manually giving a Windows computer its network settings** instead of letting DHCP choose them automatically.

Think of it like giving a house its exact address so other places know where to find it.

The computer had **two network cards**: **Ethernet** and **Ethernet 2**. Each one connected to a different network, so each needed its own IP settings.

For **Ethernet**, you had to enter:

```text
IP address:       192.168.0.254
Subnet mask:      255.255.255.0
Default gateway:  192.168.0.5
Preferred DNS:    163.128.80.93
Alternate DNS:    163.128.78.93
```

For **Ethernet 2**, you entered:

```text
IP address:       10.0.255.254
Subnet mask:      255.255.0.0
Gateway:          blank
DNS:              blank
```

Here is what each setting means in simple English:

| Setting             | Simple meaning                                            | Example                                               |
| ------------------- | --------------------------------------------------------- | ----------------------------------------------------- |
| **IP address**      | The computer's address on the network                     | Like your house address                               |
| **Subnet mask**     | Tells the computer which devices are on its local network | Like knowing which houses are in your neighborhood    |
| **Default gateway** | The router used to reach other networks or the internet   | Like the road that takes you out of your neighborhood |
| **DNS server**      | Changes website names into IP addresses                   | Turns `google.com` into an IP address                 |

The lab also asked you to use the **last valid IP address** in each subnet. For example, the Ethernet network was:

```text
192.168.0.0/24
```

The addresses work like this:

```text
192.168.0.0    = Network address
192.168.0.1
192.168.0.2
...
192.168.0.254  = Last usable address ✅
192.168.0.255  = Broadcast address
```

So you used:

```text
192.168.0.254
```

For the second network:

```text
10.0.0.0/16
```

the last usable address was:

```text
10.0.255.254
```

After configuring both network cards, you tested the connection with:

```powershell
ping 163.128.80.93
```

You received replies, which proved the computer could communicate with the DNS server.

A simple real-world example: imagine a company sets up a manager's computer. One network card connects to the normal company network and internet. 
The second network card connects to a small private network used for special equipment. 
The IT technician must assign the correct IP addresses so both connections work.

### What to remember for CompTIA A+

**Static IP = you manually enter the network information.**

Remember these four important settings:

```text
IP address     = Who am I?
Subnet mask    = Who is local?
Gateway        = How do I leave my network?
DNS            = How do I find websites by name?
```

And the final test is often:

```cmd
ipconfig /all
ping <IP-address>
```

`ipconfig /all` checks your settings, and `ping` checks whether you can communicate with another device.


---
-------------------

Perfect — this exhibit gives us the missing addresses. Use these exact values.

Setting	Ethernet	Ethernet 2
IP address	192.168.0.254	10.0.255.254
Subnet mask	255.255.255.0	255.255.0.0
Default gateway	192.168.0.5	Leave blank
Preferred DNS	163.128.80.93	Leave blank
Alternate DNS	163.128.78.93	Leave blank

The exhibit shows Bldg A Router = 192.168.0.5, so that is the default gateway. It also shows the two external DNS servers as 163.128.80.93 and 163.128.78.93.

Now do this first
Close the Exhibits window with the X.
Open Settings.
Go to Network & internet.
Click Advanced network settings.
Click More network adapter options.
Right-click Ethernet → Properties.
Click Internet Protocol Version 4 (TCP/IPv4) → Properties.
Select Use the following IP address and enter:
IP address:       192.168.0.254
Subnet mask:      255.255.255.0
Default gateway:  192.168.0.5

Then select Use the following DNS server addresses:

Preferred DNS:    163.128.80.93
Alternate DNS:    163.128.78.93

Click OK.

After that, configure Ethernet 2:

IP address:       10.0.255.254
Subnet mask:      255.255.0.0
Default gateway:  [blank]

Preferred DNS:    [blank]
Alternate DNS:    [blank]

Finally, open Command Prompt and run:

ping 163.128.80.93

You should get Reply from...

Easy way to remember
Ethernet = Company network + Internet
IP      192.168.0.254
Mask    255.255.255.0
Gateway 192.168.0.5
DNS1    163.128.80.93
DNS2    163.128.78.93

Ethernet 2 = Small internal network only
IP      10.0.255.254
Mask    255.255.0.0
Gateway BLANK
DNS     BLANK
