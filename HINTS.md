# Hints (Optional)

- Use `Invoke-WebRequest` or `Start-BitsTransfer` to download the installer
- Extract version from MSI:
    ```powershell
    $installer = New-Object -ComObject WindowsInstaller.Installer
    $database = $installer.OpenDatabase($InstallerPath, 0)
    $view = $database.OpenView("SELECT `Value` FROM `Property` WHERE `Property` = 'ProductVersion'")
    $view.Execute()
    $record = $view.Fetch()
    $version = $record.StringData(1)
    ```
- Detect installed Firefox version:
    - Look under:
      ```
      HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\Mozilla Firefox*
      ```

- Logging:
    ```powershell
    if (-not [System.Diagnostics.EventLog]::SourceExists($LogSource)) {
        New-EventLog -LogName "Application" -Source $LogSource
    }
    Write-EventLog -LogName "Application" -Source $LogSource -EntryType "Information" -EventId 1000 -Message "Message"
    ```
