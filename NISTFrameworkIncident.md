# Scenario
You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services.

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack.

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy.

---
# Incident Report Analysis
## Summary:
Recently, the organization experienced a distributed denial of service (DDoS) attack. We were able to come to this conclusion because we detected a flood of ICMP packets coming from various IP addresses. This in turn affected the internal network traffic as well, causing an interruption in access to any network resources. This DDoS attack basically  caused a halt in normal business operations, resulting in a potential loss of profits. In response to this DDoS attack, the incident management team blocked all incoming ICMP packets, halted all network services, only allowing critical network services to continue to function. When the cybersecurity team investigated the incident, they were able to conclude that the attack was an Internet Control Message Protocol (ICMP) flood attack, which is a type of denial of service (DoS) attack performed by an attacker repeatedly sending ICMP packets to a network server. They initiated this attack through an unconfigured firewall in the company's network.

## Identify:
As stated in the summary, the attacker flooded the network with ICMP packets from several IP addresses, therefore the attack was an Internet Control Message Protocol (ICMP) flood attack. This attack overwhelmed the company's internal network, causing slowdowns and halts to company operations. When auditing the internal systems and network, the team discovered that there wasn't sufficient firewall rules in place to prevent such an attack.

## Protect:
The team was able to discover that the firewall was unconfigured or was improperly configured. Therefore, the priority of the organization is to update/configure the firewall to prevent an attack like this in the future (such as limiting the rate of incoming ICMP packets), and to secure the organization's assets. It is also recommended to implement some network monitoring software, and an intrusion detection system (IDS) or an intrusion prevention system (IPS). This will detect suspicious network traffic so that the organization can act on it before it is too late.

## Detect:
We will configure the firewall to verify the source IP address in order to check for speed IP addresses on incoming ICMP packets. As stated in the previous section, we must implement a network monitoring software that will allow us to detect suspicious traffic and traffic patterns. We must also invest in an IDS/IPS so that we can monitor and filter out some traffic (especially ICMP traffic in this case) based on suspicious characteristics.

## Respond:
In future network incidents, the team will halt all network traffic, especially incoming network traffic from external networks in order to contain/isolate the threat. Secondly, identify the threat and determine the appropriate actions needed against that particular threat. Then, assuming the threat is identified and/or is contained, allow the most important and critical network traffic to continue so that company operations can still continue in the internal network. When the threat is properly contained/eliminated and proper protections/monitors are in place, restore and resume all remaining operations. Notify management and they will inform law enforcement, other organizations (if applicable), and customers about the breach.

## Recover:
As mentioned above, we will first let the critical network traffic and services come back online once the threat has been identified, and the necessary actions have been performed. After the new mitigation and prevention solutions have been implemented, the rest of the network will be let back online and organizational operations should resume normally. Any data going through the internal network during the attack should be verified since the attack may have interrupted data transfers (should be sent via email to users in the internal network)