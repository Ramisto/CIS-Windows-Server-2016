# CIS-DISA-Windows-Server-2016

This project was created to facilitate the implementation of security criteria based on CIS and DISA.

The components of this project are adapted to a Windows Server 2016 operating system that is not present in any Active Directory domain.

Here is the set of components:
- An entry in the "RestrictRemoteSAM.reg" registry
- A "GpoTemplate" directory containing the local group policy template
- A "Summary-of-GPO-settings" table summarizing the GPO settings

First of all, I invite you to look at the summary table, and advise you to create a backup of your system before starting anything! You could restore your system in case of problems.


## Installation

First step, download the project folder to your C:\ drive.

Second step, import the .reg file (line 249) :

[ Win + R ] regedit

And select "File > Import > C:\CIS-DISA-Windows-Server-2016\RestrictRemoteSAM.reg"

Third step, import the local group policy template, and apply it :

[ Win + R ] cmd

```
cd C:\CIS-DISA-Windows-Server-2016\
```
```
LGPO.exe /g C:\GpoTemplate\
```
```
gpupdate /force
```

Fourth step, check the NTFS permissions on the "Eventvwr.exe" application in the %SystemRoot%\SYSTEM32 path (line 242).


## Finally

I am aware that this project is not perfect, so don't hesitate to suggest improvements!
