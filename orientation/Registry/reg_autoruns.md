# WinRegistry - AutoRuns

## **Which Categories of AutoRun Entries Exist**

```
AutoRun entry, entry_location, image_path, category, enabled
```

## **Filter By Exclusion - By Single Field With Many Matches**

```
AutoRun entry, entry_location, image_path, category, enabled
    WHERE AutoRun category not equals "Explorer"
        AND AutoRun category not equals "Codecs"
        AND AutoRun category not equals "Logon"
        AND AutoRun category not equals "Tasks"
        AND AutoRun category not equals "Print Monitors"
        AND AutoRun category not equals "LSA Providers"
        AND AutoRun category not equals "Known DLLs"
        AND AutoRun category not equals "Network Providers"
```

## **Filter By Exclusion - By Many Fields**

```
AutoRun entry, entry_location, image_path, category, enabled
    WHERE AutoRun enabled not equals "enabled"
        AND AutoRun image_path contains "C:\Users"
        AND AutoRun image_path ends with ".exe"
            AND AutoRun category not equals "Explorer"
            AND AutoRun category not equals "Codecs"
            AND AutoRun category not equals "Logon"
            AND AutoRun category not equals "Tasks"
            AND AutoRun category not equals "Print Monitors"
            AND AutoRun category not equals "LSA Providers"
            AND AutoRun category not equals "Known DLLs"
            AND AutoRun category not equals "Network Providers"
```

## **Which Entries Exist for the Explorer AutoRun**

```
AutoRun entry, entry_location, image_path, category
    WHERE AutoRun category equals "Explorer"
```

## **Which Entries Exist for the Logon AutoRun**

```
AutoRun entry, entry_location, image_path, category
    WHERE AutoRun category equals "Logon"
```

## **Which Entries Exist for the Tasks AutoRun**
```
AutoRun entry, entry_location, image_path, category
    WHERE AutoRun category equals "Tasks"
```

## **Which Entries Exist for the Tasks AutoRun**
```
AutoRun entry, entry_location, image_path, category
    WHERE AutoRun category equals "Tasks"
```

### **Specify Tasks that launch with EXE Files**

```
AutoRun  category, entry, entry_location, image_path, launch_string, description
    WHERE AutoRun category equals "Tasks"
        AND AutoRun image_path ends with ".exe"
```

### **Specify Tasks that launch with EXE Files - From User Space**
```
AutoRun  category, entry, entry_location, image_path, launch_string, description
    WHERE AutoRun category equals "Tasks"
        AND AutoRun image_path ends with ".exe"
            AND AutoRun image_path contains "C:\Users\"
```

### **Specify Tasks that launch with EXE Files - By Description**
```
AutoRun  category, entry, entry_location, image_path, launch_string, description
    WHERE AutoRun category equals "Tasks"
        AND AutoRun image_path ends with ".exe"
            AND AutoRun description equals "FakeGoogle Installer"
```