# WinRegistry - HKLM

## **Specify a SubKey**

### **Globally Registered Services**

```
WinRegistry
    WHERE WinRegistry keypath equals "HKLM\SYSTEM\CurrentControlSet\Services"
```

### **Globally Registered System Startup & Device Config**

```
WinRegistry
    WHERE WinRegistry keypath equals "HKLM\SYSTEM\CurrentControlSet\Control"
```

### **Globally Registered Hardware Profiles**

```
WinRegistry
    WHERE WinRegistry keypath equals "HKLM\SYSTEM\CurrentControlSet\HardwareProfiles"
```

### **Globally Registered AuditPolicy Settings**
```
WinRegistry
    WHERE WinRegistry keypath equals "HKEY_LOCAL_MACHINE\SECURITY\Policy\PolAdtEv"
```

### **Globally Registered Browser Helper Objects - BHO**
```
WinRegistry
    WHERE WinRegistry keypath
        equals "HKEY_LOCAL_MACHINE\Microsoft\Windows\CurrentVersion\Explorer\Browser Helper Objects"
            OR WinRegistry keypath
                equals "HKEY_LOCAL_MACHINE\Wow6432Node\Microsoft\Windows\CurrentVersion\Explorer\\Browser Helper Objects"
```

### **Globallyser Registered Software CLSIDs**

```
WinRegistry
    WHERE WinRegistry keypath starts with "HKEY_LOCAL_MACHINE\SOFTWARE\Classes\CLSID\"
```

### **Specify a CLSID**

```
WinRegistry
    WHERE WinRegistry keypath starts with "HKEY_LOCAL_MACHINE\SOFTWARE\Classes\CLSID\"
        AND WinRegistry keyvalue contains "{42aedc87-2188-41fd-b9a3-0c966feabec1}"
```

### **Globally Registered Scheduled Tasks**

```
WinRegistry
    WHERE WinRegistry keypath
        equals "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule"
```

### **Globally Registered Chrome Browser Extensions**

```
WinRegistry
    WHERE WinRegistry keypath
        equals "HKEY_LOCAL_MACHINE\Software\Google\Chrome\Extensions"
        OR WinRegistry keypath equals "HKEY_LOCAL_MACHINE\Software\Wow6432Node\Google\Chrome\Extensions"
```

### **Globally Registered Local User Accounts**
```
WinRegistry
    WHERE WinRegistry keypath
        equals "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList"
```