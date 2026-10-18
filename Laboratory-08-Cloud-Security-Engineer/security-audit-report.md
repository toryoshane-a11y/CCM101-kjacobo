# Security Audit Report

## The Principle of Least Privilege (PoLP)
The Principle of Least Privilege means giving a user, application or service only the permissions it needs to do its job, and nothing more. It matters for cloud user accounts because if an account is stolen or misused, the damage is limited to what that account was allowed to do. An intern who can only read files, for example, cannot delete a production database even if their password leaks.

## Attack Surface
The attack surface of a virtual machine is the total number of points where an attacker could try to get in. This includes open network ports, running services, installed software, and user accounts with remote access. Every extra open port or unused service adds to the attack surface, so keeping it small leaves fewer ways in.

## Default Deny Policy
A Default Deny policy blocks all incoming traffic unless a rule explicitly allows it. This is safer than blocking specific hackers one by one because attackers can change their addresses constantly, and a blocklist can never cover every threat. With Default Deny, anything not approved is rejected, so a forgotten or unknown service stays protected.
