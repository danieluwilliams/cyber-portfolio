# Linux Audit Intrusion Detection Lab

## Overview
This lab demonstrates how Linux audit rules can be used to monitor sensitive files and detect unauthorized modifications.

Using the auditd framework, file access events were logged and analyzed to determine which attack programs modified protected files.

## Setup

Configured an audit rule to monitor a protected directory:

sudo auditctl -w /home/codepath/project2-main/protected_files -p rwxa

This rule logs:
- Read
- Write
- Execute
- Attribute changes

## Simulated Attacks

Three attack programs were executed:

./attack-a  
./attack-b  
./attack-c  

These programs attempted to modify files inside the protected directory.

## Log Analysis

Audit logs were searched using:

sudo ausearch -ts recent -i

The results showed which attack modified which file.

## Findings

| Attack Program | File Modified |
|----------------|---------------|
| attack-a | cloudia.txt |
| attack-b | oakley.txt |
| attack-b | squeaky.txt |
| attack-c | precipitation.csv |

## Skills Demonstrated

- Linux security monitoring
- auditd configuration
- log analysis
- intrusion detection techniques

## Tools

- Linux
- auditctl
- ausearch
