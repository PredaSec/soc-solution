# SOC Solution 

Technologies used :

- [Wazuh](https://github.com/wazuh/wazuh)
- [TheHive](https://github.com/TheHive-Project/TheHive)
- [ELK](https://www.elastic.co/fr/elastic-stack)
- [MISP](https://github.com/MISP/MISP)
- [Atomic Red Framework](https://github.com/redcanaryco/atomic-red-team)
- [Mitre Framework](https://attack.mitre.org)

## Architecture 
 
![Architecture](/img/architecture.png)

In this solution, we needed a modern architecture that emphasizes centralized data
correlation and ease of access. We needed to have a dynamic architecture that offers a way to:
- Collecting and correlating data in a centralized system.
- Ability to parse and visualize data and extract meaningful security alerts and events.
- Collect System events from various endpoints with the ability of instant detection and
active response capabilities.
- Create cases and manage incidents with a good ticketing and incident response
solution.
- Automate the process of Threat intelligence and enrich security events.
- Actively respond to threats and interact with the constituency while actively
responding and detecting threats.

## Techs Presentation

### Wazuh

![Wazuh](/img/wazuh.png)

Wazuh provides real-time threat detection and each Wazuh server is connected directly to the MITRE ATT&CK database, providing real-time updates of threats identified across the Wazuh user community. Wazuh agents are available for a range of endpoint OSs

### ELk 

![ELK](/img/elastic%20stack.png)

Elastic stack is a powerful open-source platform for searching, analyzing, and visualizing data. It is referred to as ELK Stack because it’s made of core components.

### TheHive

![TheHive](/img/thehive.png)

TheHive is a scalable Security Incident Response Platform, tightly integrated with MISP (Malware Information Sharing Platform), designed to make life easier for SOCs, CSIRTs, CERTs and any information security practitioner dealing with security incidents that need to be investigated and acted upon swiftly.

### MISP

Built on an open-source foundation, Malware Information Sharing Platform or MISP
offers APIs for seamless integration with existing security ecosystem, whether it's SIEMs, SOAR platforms, or custom security tools.

## Wazuh Active Response

Active response cycle starts by detection attacks and anommalies using TheHive dashboard that will be providing alerts from Wazuh server. 

> Alerts in Wazuh are displayed with a Mitre ID
> that you can inspect in Mitre platform

After fully investigating the attack you can define active response rule in `/etc/ossec.conf` file.

Last but not least, you can test you EDR efficiency by using AtomicRedTeam predefined TTPs used by threat actors mapped to the MITRE ATT&CK framework.
