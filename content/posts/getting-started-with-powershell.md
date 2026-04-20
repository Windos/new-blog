---
title: "Getting Started with PowerShell"
date: 2026-04-16T10:00:00Z
draft: false
tags: ["PowerShell", "Automation"]
---

PowerShell is an incredibly powerful task automation and configuration management program from Microsoft. Today, we're going to dive into some of the basics.

## The Pipeline

One of the best features of PowerShell is its object-oriented pipeline. Unlike traditional shells that pass text strings, PowerShell passes .NET objects.

```powershell
Get-Process | Where-Object { $_.WorkingSet -gt 100MB } | Sort-Object WorkingSet -Descending
```

This snippet retrieves all running processes, filters for those consuming more than 100MB of memory, and sorts them by memory usage.

## Basic Scripting

Writing a PowerShell script is straightforward. Here is a simple function to check if a website is up:

```powershell
function Test-Website {
    param (
        [string]$Url
    )
    
    try {
        $response = Invoke-WebRequest -Uri $Url -UseBasicParsing
        if ($response.StatusCode -eq 200) {
            Write-Output "Website $Url is up!"
        }
    } catch {
        Write-Error "Website $Url is down or unreachable."
    }
}

Test-Website -Url "https://toastit.dev"
```

Stay tuned for more advanced PowerShell topics!
