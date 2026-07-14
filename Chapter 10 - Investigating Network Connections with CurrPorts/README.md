# Chapter 10 - Investigating Network Connections with CurrPorts

## Overview

This chapter demonstrates how SOC analysts use CurrPorts to investigate active network connections. By reviewing connection details, analysts can identify which applications are communicating over the network and determine whether the activity is legitimate or suspicious.

---

## Investigation Objective

The objective of this investigation is to:

- Identify active network connections.
- Determine which process owns each connection.
- Review connection properties.
- Verify the executable path.
- Determine whether the connection is expected.

---

## Investigation Steps

### Step 1 - Review Active Connections

Open CurrPorts and review the list of active TCP and UDP connections.

Pay attention to:

- Process Name
- Process ID (PID)
- Protocol
- Local Address
- Remote Address
- Remote Port
- Connection State

### Screenshot

![CurrPorts Overview](currports_overview.png)

---

### Step 2 - Investigate a Connection

Select an active connection.

For this investigation, I reviewed a Microsoft Teams (or Microsoft Edge) connection.

Open the connection properties by:

- Double-clicking the connection

or

- Right-click → Properties

### Screenshot

![Connection Properties](edge_connection_properties.png)

---

### Step 3 - Verify the Process

Review:

- Process Name
- Process Path
- Company Name
- File Version
- Local Address
- Remote Address
- Remote Port
- State

Verify that:

- The executable is located in a trusted directory.
- The company is legitimate.
- The connection is expected.

---

## Analysis

During this investigation I observed:

- The selected process belonged to a legitimate Microsoft application.
- The executable path pointed to the official installation directory.
- The company information identified Microsoft Corporation.
- The connection state was **Established**, indicating active communication.
- The remote connection used **HTTPS (Port 443)**, which is normal for secure web traffic.

No suspicious behavior was identified during this investigation.

---

## What to Look For

When investigating connections, review:

- Unknown process names
- Executables located in Temp or AppData
- Unknown company names
- Unexpected outbound connections
- Suspicious remote IP addresses
- Uncommon remote ports
- Multiple connections from unknown applications

---

## Red Flags

Investigate immediately if you observe:

- Unknown executable communicating with the Internet
- Missing or unknown company information
- Executables running from user profile folders
- Connections to suspicious external IP addresses
- Multiple outbound connections from unfamiliar processes
- Unexpected network activity after startup

---

## Investigation Checklist

Before closing an investigation, verify:

- ✓ Process Name
- ✓ Process Path
- ✓ Company Name
- ✓ Local Address
- ✓ Remote Address
- ✓ Remote Port
- ✓ Connection State
- ✓ Is the activity expected?

---

## Key Takeaways

- CurrPorts links network connections to running processes.
- Reviewing connection properties helps validate whether activity is legitimate.
- Executable paths and company information are useful indicators of legitimacy.
- Established connections over HTTPS (Port 443) are common for trusted applications.
- Unknown processes, unusual paths, or unexpected remote connections should be investigated further.

