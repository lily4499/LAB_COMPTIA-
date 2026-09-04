
<img width="317" height="401" alt="image" src="https://github.com/user-attachments/assets/ea381e7d-20d9-4400-946b-8aa55c392835" />



This lab was about **connecting a computer to the Internet using a cable modem**.

### The situation

You were acting like the IT technician for a **small office/home office, called SOHO**.

The company had just signed up for cable Internet.

The Internet company had already done two things:

* installed the cable line into the building
* gave you a modem that was already configured

That means you did **not** have to set IP addresses, DNS, or other network settings.

Your job was only to **connect the correct cables to the correct ports**.

A simple example is setting up Internet at home after the cable company gives you a modem.

### What needed to be done

You had to make three main connections:

```text
ISP wall connection
        |
        | RG-6 coaxial cable
        |
   Cable Modem
        |
        | Cat6a Ethernet cable
        |
     Computer
```

And the modem also needed power:

```text
Wall power outlet
        |
        | AC-to-DC power adapter
        |
   Cable Modem
```

### How you did it

First, you added the **cable modem** to the workspace.

Then you used an **RG-6 coaxial cable**.

One end went into the wall's **F-type cable outlet**.

The other end went into the modem's **Cable Port**.

That connection is:

```text
Cable company / ISP
        ↓
Wall coax outlet
        ↓
RG-6 cable
        ↓
Cable modem
```

Next, you used a **Cat6a Ethernet cable with RJ-45 connectors**.

One end went into the computer's **NIC/Ethernet port**.

The other end went into the modem's **LAN port**.

```text
Cable Modem LAN port
        |
        | Cat6a Ethernet
        |
Computer NIC
```

Then you used the **AC-to-DC power adapter**.

One end connected to a free wall power outlet, such as **AC1**.

The other end connected to the modem's **DC power port**.

```text
AC wall outlet
      |
Power adapter
      |
Cable Modem
```

Once the modem had all three connections, the computer could reach the Internet.

### What each cable was for

| Cable                      | What you used it for                                        |
| -------------------------- | ----------------------------------------------------------- |
| **RG-6 coaxial**           | Brings the cable Internet signal from the wall to the modem |
| **Cat6a Ethernet / RJ-45** | Connects the modem to the computer                          |
| **AC-to-DC adapter**       | Gives electricity to the modem                              |

### Real-world example

Imagine Comcast installs cable Internet in your house.

The cable coming from the wall does not normally plug directly into your computer.

Instead:

```text
Comcast
   ↓
Coax wall cable
   ↓
Modem
   ↓
Ethernet cable
   ↓
Computer
```

The modem is like a **translator** between the cable company's network and your computer.

### What to remember for CompTIA

The biggest lesson is knowing **which cable goes where**:

```text
ISP → RG-6 coax → Modem
Modem → RJ-45 Ethernet → Computer
Wall power → AC/DC adapter → Modem
```

A very easy memory trick is:

**Coax brings Internet IN.
Ethernet sends network TO the computer.
Power makes the modem work.**
