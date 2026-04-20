---
title: "Integrating Ansible and PowerShell"
date: 2026-04-14T09:30:00Z
draft: false
tags: ["Ansible", "PowerShell", "Windows"]
---

Did you know you can use Ansible to manage Windows machines using PowerShell? It's a match made in heaven for cross-platform environments.

## Setting up WinRM

Ansible communicates with Windows machines over WinRM instead of SSH. You can configure WinRM using a script provided by the Ansible community:

```powershell
Invoke-WebRequest -Uri https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1 -OutFile ConfigureRemotingForAnsible.ps1
powershell -ExecutionPolicy RemoteSigned .\ConfigureRemotingForAnsible.ps1
```

## Running PowerShell from Ansible

You can execute arbitrary PowerShell scripts using the `win_powershell` module:

```yaml
---
- name: Run PowerShell script
  hosts: windows
  tasks:
    - name: Get Disk Space
      win_powershell:
        script: |
          Get-WmiObject Win32_LogicalDisk | Select-Object DeviceID, FreeSpace, Size
```

This combination unlocks powerful automation capabilities across both Linux and Windows ecosystems.
