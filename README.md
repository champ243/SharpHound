# SharpHound

![GitHub all releases](https://img.shields.io/github/downloads/SpecterOps/SharpHound/total)

## Get SharpHound

The latest build of SharpHound will always be found [here](https://github.com/SpecterOps/SharpHound/releases).

To determine the SharpHound version compatible with a deployed BloodHound CE instance, login to BloodHound CE's web UI and click on ⚙️ (Settings) → Download Collectors. Then, click either the "Download SharpHound" button in the user interface or use the displayed SharpHound version to download the appropriate [release binary](https://github.com/SpecterOps/SharpHound/releases). Alternatively, compile a SharpHound binary from the corresponding release commit.

## Documentation

Please refer to the [SharpHound section](https://bloodhound.specterops.io/collect-data/ce-collection/sharphound), part of the [BloodHound Community Edition documentation](https://bloodhound.specterops.io/home). 

## Compile Instructions

To build this project, use .net 5.0 and run the following:

```
dotnet restore .
dotnet build
```

## Requirements

SharpHound is designed targeting .Net 4.6.2. SharpHound must be run from the context of a domain user, either directly through a logon or through another method such as RUNAS.

# SharpHound

```csharp
dotnet restore .
dotnet build
```

# CLI Arguments
The listing below details the CLI arguments SharpHound supports. Additional details about these options can be found in the [BloodHound CE Collection documentation](https://bloodhound.specterops.io/collect-data/ce-collection/sharphound-flags).
```
  -c, --collectionmethods    (Default: Default) Collection Methods: Container, Group, LocalGroup, GPOLocalGroup,
                             Session, LoggedOn, ObjectProps, ACL, ComputerOnly, Trusts, Default, RDP, DCOM, DCOnly, UserRights, 
                             CARegistry, DCRegistry, CertServices, WebClientService, NTLMRegistry,SMBInfo,LdapServices

  -d, --domain               Specify domain to enumerate

  -s, --searchforest         (Default: false) Search all available domains in the forest

  --stealth                  Stealth Collection (Prefer DCOnly whenever possible!)

  -f                         Add an LDAP filter to the pregenerated filter.

  --distinguishedname        Base DistinguishedName to start the LDAP search at

  --computerfile             Path to file containing computer names to enumerate

  --outputdirectory          (Default: .) Directory to output file too

  --outputprefix             String to prepend to output file names

  --cachename                Filename for cache (Defaults to a machine specific identifier)

  --memcache                 Keep cache in memory and don't write to disk

  --rebuildcache             (Default: false) Rebuild cache and remove all entries

  --randomfilenames          (Default: false) Use random filenames for output

  --zipfilename              Filename for the zip

  --nozip                    (Default: false) Don't zip files

  --trackcomputercalls       (Default: false) Adds a CSV tracking requests to computers

  --zippassword              Password protects the zip with the specified password

  --prettyprint              (Default: false) Pretty print JSON

  --ldapusername             Username for LDAP

  --ldappassword             Password for LDAP

  --domaincontroller         Override domain controller to pull LDAP from. This option can result in data loss

  --ldapport                 (Default: 0) Override port for LDAP

  --secureldap               (Default: false) Connect to LDAP SSL instead of regular LDAP

  --disablecertverification  (Default: false) Disable certificate verification for secure LDAP

  --disablesigning           (Default: false) Disables Kerberos Signing/Sealing

  --skipportcheck            (Default: false) Skip checking if 445 is open

  --portchecktimeout         (Default: 500) Timeout for port checks in milliseconds

  --skippasswordcheck        (Default: false) Skip PwdLastSet age check when checking computers

  --excludedcs               (Default: false) Exclude domain controllers from session/localgroup enumeration (mostly for
                             ATA/ATP)

  --throttle                 Add a delay after computer requests in milliseconds

  --jitter                   Add jitter to throttle (percent)

  --threads                  (Default: 50) Number of threads to run enumeration with

  --skipregistryloggedon     Skip registry session enumeration

  --overrideusername         Override the username to filter for NetSessionEnum

  --realdnsname              Override DNS suffix for API calls

  --collectallproperties     Collect all LDAP properties from objects

  -l, --Loop                 Loop computer collection

  --loopduration             Loop duration (hh:mm:ss - 05:00:00 is 5 hours, default: 2 hrs)

  --loopinterval             Add delay between loops (hh:mm:ss - 00:03:00 is 3 minute)

  --statusinterval           (Default: 30000) Interval in which to display status in milliseconds

  --localadminsessionenum    Specify if you want to use a dedicated LOCAL user for session enumeration

  --localadminusername       Specify the username of the localadmin for session enumeration

  --localadminpassword       Specify the password of the localadmin for session enumeration

  -v                         (Default: 2) Enable verbose output. Lower is more verbose

  --help                     Display this help screen.

  --version                  Display version information.
```
