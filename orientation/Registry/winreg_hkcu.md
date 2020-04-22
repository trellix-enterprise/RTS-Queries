# WinRegistry - HKCU

Reference the HKLM winreg guide to expand searches, but rather use the `HKEY_CURRENT_USER` or
`HKCU` prefix in your query for the key_path param.

## **Specify a SubKey**

### **User Registered StartUp Items**

```
WinRegistry
    WHERE WinRegistry keypath equals "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run"
```

### **Specify - SINGLE IoC Simulation**

```
WinRegistry
    WHERE WinRegistry keypath equals "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run"
        AND WinRegistry keyvalue equals "foo"
```

### **Specify - MANY IoC Simulation**
```
WinRegistry
    WHERE WinRegistry keypath equals "HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run"
        AND WinRegistry keyvalue equals "Skype"
            OR WinRegistry keyvalue contains "Google"
            OR WinRegistry keyvalue contains "zoom"
            OR WinRegistry keyvalue contains "Zoom"
```

### **User Registered Software CLSIDs**

```
WinRegistry
    WHERE WinRegistry keypath equals "HKEY_CURRENT_USER\Software\Classes\CLSID\"
```

### **User Registered Chrome Browser Extensions**

```
WinRegistry
    WHERE WinRegistry keypath
        equals "HKEY_CURRENT_USER\Software\Google\Chrome\Extensions"
        OR WinRegistry keypath equals "HKEY_CURRENT_USER\Software\Wow6432Node\Google\Chrome\Extensions"
```
