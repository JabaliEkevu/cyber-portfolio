# TryHackMe: Linux PrivEsc
**Room URL:** https://tryhackme.com/room/linuxprivesc  
**Completed on:** July 2024  
**Time spent:** 90 minutes

## Objective
Practice Linux privilege escalation techniques on a Debian virtual machine. Enumerate system configurations and exploit misconfigurations to obtain root access.

## Tools used
- Linux terminal (bash)
- sudo
- find
- grep
- exploit scripts (LinPEAS or manual methods)

## Steps I took (commands + purpose)
1. Initial enumeration
   - `uname -a` (check kernel)
   - `id` (check current user)
   - `ps aux` (view running processes)
2. Check sudo permissions
   - `sudo -l` (identify misconfigurations)
3. Search for SUID binaries
   - `find / -perm -4000 -type f 2>/dev/null`
4. Identify vulnerable binary / escalation path
   - (Describe what you found. Example: a writable script or a service running as root.)
5. Privilege escalation
   - (Paste the command used to get root, e.g.)
   - `./vulnerable_binary` or `sudo vim -c '!sh'`
6. Verification
   - `whoami` (confirm root)
   - `id` (confirm privileges)
   - Retrieved flag: `/root/root.txt` (do not paste the contents)

## Findings / Evidence
- Vulnerability: (short description)
- Output showing escalation success:
  - `whoami` = root
  - (Screenshot references below)

## Conclusion / Remediation
- Remove unnecessary SUID binaries
- Harden sudo rules (least privilege)
- Regular permission audits

## What I learned
- How to enumerate Linux users and SUID binaries
- How to use sudo -l to detect escalation paths
- Why least-privilege permissions are critical to server security

## Artifacts
Screenshots:
- `step1.png`
- `step2.png`
