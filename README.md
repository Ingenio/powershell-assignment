# PowerShell Framework Challenge – Firefox Installer

## Objective
Complete the PowerShell script to install or upgrade Mozilla Firefox using the official online MSI.

## Requirements
- Script should:
  - Download latest Firefox MSI
  - Detect currently installed Firefox version
  - If `-Upgrade` is specified, only install if remote version is newer
  - Log all activity to the Windows Application event log
- Focus on clean, modular code with robust error handling

## Download URL
```
https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=en-US
```

## How to Run

```powershell
.\Install-Firefox.ps1
.\Install-Firefox.ps1 -Upgrade
```

## Submission
Submit your completed `.ps1` file. Include any notes or assumptions.

## Bonus
- Parameter validation
- Implement detailed error logs or retry logic
- Cleanup downloaded files
