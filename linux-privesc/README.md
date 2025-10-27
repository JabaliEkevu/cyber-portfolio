# TryHackMe: Linux PrivEsc
This hands-on room demonstrates my ability to investigate Linux systems, identify a privilege escalation vulnerability, and apply practical defense recommendations aligned with SOC analyst responsibilities.

**Room URL:** https://tryhackme.com/room/linuxprivesc  
**Completed on:** 2024-07-09
**Time spent:** ~2 hours

**Badge / Profile:** https://tryhackme.com/p/MdukuziWaWadukuzi

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
## Findings / Evidence
The escalation was possible because a misconfigured SUID binary allowed regular users to execute a process with root privileges. By identifying this binary during enumeration and executing it, I elevated privileges to root and accessed sensitive system files such as `/root/root.txt`. This demonstrates why SUID binaries should be tightly controlled and regularly audited.


## Conclusion / Remediation
- Remove unnecessary SUID binaries
- Harden sudo rules (least privilege)
- Regular permission audits

## What I learned
## What I learned
- How to systematically enumerate Linux hosts to identify privilege escalation paths
- How SUID binaries and misconfigured sudo rules can allow unauthorized access
- How to think like a defender by identifying misconfigurations before they are exploited
- Why least-privilege permissions and regular audits are essential for secure Linux systems


## Artifacts
Screenshots:
- `step1.png`
- `step2.png`
