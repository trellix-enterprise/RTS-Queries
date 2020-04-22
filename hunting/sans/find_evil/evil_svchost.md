# SANS FindEvil Poster

In some cases, a SOC approaches monitoring proactively through dedicated threat hunting expertise.

One proactive approach is to leverage public knowledge of how the Operating System works by design, and hunt (search) for patterns
violating the design. The `SANS FindEvil` poster is an amazing resource for defenders to leverage for proactive hunting and finding
anomalous patterns, like when a program impersonates `svchost.exe`.

In such a case, the `SANS` poster teaches us that a legitimate SVCHOST should mainly be launched by the designated SERVICES.EXE process in Windows.


Source: [SANS - FindEvil](https://digital-forensics.sans.org/media/DFPS_FOR508_v4.3_12-18.pdf)
<br/>
<hr/>

## **Imposter SVCHOST**

### **Identify Programs Posing as SVCHOST**

```
 ProcessHistory parentname, name, id, cmdline
    WHERE ProcessHistory parentname not equals "services.exe"
        AND ProcessHistory name equals "svchost.exe"
```

![image](https://user-images.githubusercontent.com/11415591/80018571-2fd1c100-84a4-11ea-89db-b978ee36646b.png)

<br />

Now Add the Hostname where execution occurred

```
HostInfo hostname
    AND ProcessHistory parentname, name, id, cmdline
        WHERE ProcessHistory parentname not equals "services.exe"
            AND ProcessHistory name equals "svchost.exe"
```

![image](https://user-images.githubusercontent.com/11415591/80019341-5ba17680-84a5-11ea-94de-22c21399920a.png)

<hr/>

## **Abnormal Process Creation Via WMI**

Identify which processes are running under WMIPRVSE resulting from the command

```powershell
# What happens after an adversary runs this command, who is the parent?
C:\> wmic process call create foo.exe
```

```
HostInfo hostname
    AND ProcessHistory parentname, name, id, cmdline
        WHERE ProcessHistory parentname equals "wmiprvse.exe"
```

![image](https://user-images.githubusercontent.com/11415591/80020779-91475f00-84a7-11ea-862e-35a1b181d867.png)