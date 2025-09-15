# Threat Hunting Prompts

## SecOps Hunting

* Show me all failed login attempts from IP address
```
Show me all failed login attempts from IP addresses that have not previously authenticated successfully to this system within the past 30 days. Include the source IP, account name, and timestamp.
```

* Unusual traffic patterns
```
Identify unusual network traffic patterns, such as spikes in data transfer or connections to unfamiliar IP addresses in the past 30 days
```

* Suspicious Process Execution
```
Show me all processes launched from temp directories, user profile AppData in the last 7 days. Inlcude the process name, associated username, full commandline, and timestamp. Examine any suspicious behaviours - such as command line utilities - and enrich these indicators with gti. Provide the child processes should gti returns a verdict of suspicious or malicious. 
```

## Threat Intelligence
* Understanding Malware
```
Tell me more about Ransomhub Ransomware. Include their TTPs, threat actors observed to have used them, and any known IOCs first seen in the past 30 days. 
```

* Understanding Campaigns (Strategic) 
```
Based on this report <insert link>, summarise the report for a CISO. Include their TTPs
```

* Understanding Vulnerabilities
```
You are a cybersecurity analyst focusing on vulnerability management, and you are expected to update your CISO on the latest vulnerability trends. Focus on vulnerabilities actively exploited in the wild and those with a high potential for causing significant impact. Provide a summary of each vulnerability, its potential impact, and recommended mitigation strategies. Use key insights such as CISA Known Exploited Vulnerabilities (KEV) catalog, Common Vulnerability Scoring System (CVSS), as well as the Exploit Prediction Scoring System (EPSS).
```

* Understanding Campaigns + Hunting Packages (Operational / Tactical)
```
Based on this report <insert link>, summarise the report for a threat intelligence analyst. Please output the following: - any ttps/behaviours in the report - any indicators / iocs in the report in a table format. If there are any TTPs that we can use, convert them into a cyber threat hunting package based on YARA-L. Leverage Sysmon event data primarily when creating YARA-L rules
```

* Understanding campaigns for hypothesis
``` 
You are a threat hunter. Provide a list of hypotheses that we can test based on the following campaign report <insert link>. 
For each hypothesis, provide a list of data sources that we can use to test the hypothesis. 

<table_structure>
| Procedure | Description | Logs |
|-----------|-------------|------|
| Short title | Detailed description with patterns | Relevant logs and Event IDs |
</table_structure>

- Provide detailed technical information
- Structure the information according to the provided table structure format
- Include only actionable procedures for threat hunting
- Focus on specific search patterns
- Avoid generic or ambiguous information
- Include citations
```

* Understanding reports, and pulling IOCs and any rules
```
You are a threat hunter. Based on this report <insert link>, summarise the report for a threat intelligence analyst. Please output the following: 
  - any ttps/behaviours in the report 
  - any indicators / iocs in the report in a table format. 
If there are any rules such as YARA rules, automatically push them to my Livehunt rule on GTI 
```

* Ransomware Victims / Affliates Profile
```
Analyse Akira Ransomware Victims and Tactics.

# Follow up prompt if need be
Based on what was provided, provide some threat hunting hypotheses.
```

## Vulnerabilities

* Understanding specific vulnerabilities

```
Tell me about the log4j vulnerability. Include the CVE number, CVSS score, and a summary of the vulnerability. Provide recommendations on what I need to do to remediate this vulnerability. Check if I have any open cases or if my scc shows any alerts related to it
```

```
Tell me about the cve-2025-31324 vulnerability. Include the CVE number, CVSS score, and a summary of the vulnerability. Explain in point form, who has been observed exploiting this vulnerability, why this vulnerability is critical, and the risk associated with it. 
  - Provide recommendations on what I need to do to remediate this vulnerability. 
  - Check if I have any open cases or alerts based on the file hashes in the report. 
  - Structure the response for a CISO
```

