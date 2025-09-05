# Scenario
You are a newly hired cybersecurity analyst for an e-commerce company. The company stores information on a remote database server, since many of the employees work remotely from locations all around the world. Employees of the company regularly query, or request, data from the server to find potential customers. The database has been open to the public since the company's launch three years ago. As a cybersecurity professional, you recognize that keeping the database server open to the public is a serious vulnerability.

You are tasked with completing a vulnerability assessment of the situation to communicate the potential risks to decision makers at the company. You must create a written report that explains how the vulnerable server is a risk to business operations and how it can be secured.
# Vulnerability Assessment Report
## System Description
The server hardware consists of a powerful CPU processor and 128GB of memory. It runs on the latest version of Linux operating system and hosts a MySQL database management system. It is configured with a stable network connection using IPv4 addresses and interacts with other servers on the network. Security measures include SSL/TLS encrypted connections.
## Scope
The scope of this vulnerability assessment relates to the current access controls of the system. The assessment will cover a period of three months, from June 2024 to August 2024. NIST SP 800-30 Rev. 1 is used to guide the risk analysis of the information system.
## Purpose
Because there is only one server used in business operations, this server is extremely valuable to the business. Any security event that affects the server could cause a disruption in business operations and other issues (monetary loss, loss of reputation, etc.); therefore, it is very, very important that the server's operations do not get disrupted in any way and its data is properly secured. The purpose of this vulnerability assessment is to secure the server to ensure its operations does not get interrupted by any potential malicious actors, be it internal or external, by assessing the access controls.
## Risk Assessment
| Threat source | Threat event | Likelihood | Severity | Risk (likelihood x severity) |
| :-------------- | :---------------- | :-------------- | :----------- | :------ |
| Hacker | Obtain sensitive information via exfiltration | 3 | 3 | 9 |
| Employee | Alter/delete critical information | 2 | 3 | 6 |
| Competitor | Conduct Denial of Service (DoS) attacks | 2 | 3 | 6 |

## Approach
The approach I used was the fact that the server is public and I considered potential threats to a server that is public. Although the server being "public" is still a bit vague, I am only assuming it means the server is public knowledge, or known to the public. Since the server is public, a hacker might gain knowledge of it and attempt to obtain sensitive information stored in it. The likelihood of this is very likely, it would severely disrupt business operations and impact its reputation. An employee may go rogue and alter/delete critical information in the server since the server is public and easily accessible. There was no mention of the principle of least privilege and the separation of duties being implemented in the organization, so the likelihood of this happening is likely but an employee going rogue is quite rare. However, the severity of this event could cause significant business disruptions since a lot of sensitive data is stored in this server. A competitor might gain knowledge of the server just like how hackers would and conduct DoS attacks, but the likelihood of this happening is, in my opinion, quite rare but not unlikely. A DoS attack would definitely cause significant business operation disruptions so it was given a high severity score.

## Remediation strategy
Having proper storage encryption (like using public key infrastructure) on the server's data would help prevent data exfiltration from potential hackers. Implementing the principle of least privilege and the separation of duties would prevent rogue employees from altering/deleting sensitive information in the server. Configuring a proper firewall would prevent competitors from conducting DoS/DDoS attacks on the server.