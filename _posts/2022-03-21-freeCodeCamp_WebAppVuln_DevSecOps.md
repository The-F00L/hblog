---
title: (N)(FCC)Web App Vulnerabilities - DevSecOps Course for Beginners
published: true
---

# Web App Vulnerabilities - DevSecOps Course for Beginners
### YouTube video: [Web App Vulnerabilities - DevSecOps Course for Beginners](https://www.youtube.com/watch?v=F5KJVuii0Yw)

----
- ## Vulnerability:
	- system misconfig -> get access
	- ##### OWASP
	- ##### CWE
	- ##### MITRE
	- ###  Type:
		- ### Porous Defense
			- allow user to bypass auth
			- weak password encoding
			- not protected credentials
			- missing auth
			- mis conf permissions
			- not expiring session
				- ### Possiable attack:
					- credentail stuffing attack
					- hijackiing session id 
					- steal login credentail
					- men in the middle attack
		- ### Risky Resource Management:
			- memory (BufferOverFlow)
			- functions (Path/Directory Traversal)
			- open-source frameworks
		- ### Insecure Interaction Between Components:
			- introduce vuln between services-threads-processs
				- Cross Site Scripting
				- Cross Site Requests Forgery
			- Attack:
				- Backdoor Attacks
				- Scripting Attacks
				- Worms
				- Trojan Horses
				- Other Exploit
- #### Exploit:
	- takes advantage of a software vulnerability or security flaw
	- exploit kits
- #### Threat:
	- event 

----
# Top Vulnerability: Broken Access Control 
----
# DevSecOps
- CI/CD
- automation testing
- [SNYK](https://snyk.io/)
- SES tools
- sandbox
- Dynamic Application Scanning Tools (DAST)
- Custom Code < Open Source Code
- vuln in dependency
- to Cloud
- Benefits 
	- Fast delivery 
	- Enhancing the value of DevOps
	- Improving security integraetion and place
	- Improved security posture
	- Reduced costs
	- Enabling greater overall business succes
- \*Hands on practice*
	- burp suite
- #### Containers:
	- minimize footprint(available tools)
	- secure supply chain
	- build strategies
	- layer housekeeping
	- don't run as root
	- privileged containers
	- drop capabilities?
	- read only root filesystem
	- deploy from known sources
	- ##### Kubernetes:
		- secrets: encrypted and RBAC applied
		- SecurityContext 
		- Network Policy: Zero-trust
		- Enforcement: OPA(Gatekeeper),Kyverno,etc
- #### Key Takeaways
- Feedback Loop
- Empower developers to be proactive
- Defence in depth