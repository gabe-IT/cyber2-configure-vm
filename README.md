# Lab Setup: Disabling Windows Firewall, Installing SQL Server, and Creating Vulnerabilities

This guide details the steps to disable the Windows Firewall, install SQL Server, and create specific vulnerabilities on a Windows 10 Pro VM. You will also test connectivity with a Linux VM.

## Prerequisites

- **Windows VM** (`windows-vm`)
- **Linux VM** (`linux-vm`)

## Steps

### 1. Remote into Windows VM
- Use Remote Desktop Protocol (RDP) to connect to `windows-vm`.

### 2. Disable Windows Firewall
- Open the firewall management tool: `wf.msc`.
- Turn off the Windows Firewall for all profiles.
- **Note**: After disabling the firewall, attempt to ping the `windows-vm` from another machine to confirm the firewall is disabled.

### 3. Install SQL Server 2019 Evaluation
- Download and install SQL Server Evaluation [here](https://www.microsoft.com/en-us/evalcenter/evaluate-sql-server-2019).
- During installation, at the "Database Engine Configuration" step, select **Mixed Mode**.
  - **Username**: `sa`
  - **Password**: `Cyberlab123!`
  
### 4. Install SQL Server Management Studio (SSMS)
- Download and install SSMS from [this link](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms).
- SSMS provides a user-friendly GUI to interact with SQL Server.

### 5. Enable SQL Server Logging
- Enable logging for SQL Server to be sent to Windows Event Viewer. This requires editing the registry (`hkey`). Follow the reference guide or video provided in the lab materials.
- After enabling logging, test SQL Server to ensure logs are being captured correctly.

### 6. Test Connectivity with Linux VM
- **Ping**: Test connectivity by pinging `linux-vm` from `windows-vm`.
- **SSH**: Attempt to log into `linux-vm` via SSH.
