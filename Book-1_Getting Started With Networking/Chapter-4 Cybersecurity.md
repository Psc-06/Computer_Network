
## Two pillars of Cybersecurity
There are two basic elements that you must consider as part of your cybersecurity plan:
- **Prevention** : The first pillar of cybersecurity is the tools and technology that you can deploy to prevent bad actors from penetrating your network and stealing or damaging your data. This includes firewalls , antivirus programs antispam program.
- **Recovery** : The second pillar of cybersecurity is necessary because the first pillar isn't always successful. So you need to have technology and plans in place to quickly recover from them when they hit. This includes things such as creating backup copies of data 
### Prevention
The foundation of the IT environment, the threats it exposed to and the vulnerabilities it present is an asset management system that leads your keep track of absolutely everything that's connected to your network. This inventory includes at least the following: 
- All the hardware connected to your network
- All the software connected to your network
- All the people connected to your network, typically represented by active directory accounts

**Preventive measures to protect Each asset are:**
- Firewalls
- Wi-Fi Security
- Antivirus Software
- Antispam Software
- Strong Passwords
- Multifactor Authentication
- Data Protection 
- Encryption
	-Encryption refers to the process of encoding data so that it can be read only by those who posses the secret encryption key. it is one of the most important aspects of data security
	-One common way to use encryption is on wireless networks where all data should be encrypted. This type of encryption is called data-in-flight encryption because it encrypts data while it's in transit from one computer or device to another.
	-When the encrypt data that resides on disk drives, this type of encryption is called data-at-rest encryption.
- User Life-cycle Management 
	-It means that it a document or policy that ensures that when a user leaves the organization the user's access is terminated
- Auditing
- User Training
- Physical Security
### Recovery
The most important aspect of recovery is to plan for it in advance. Don't wait until after a cybersecurity has succeeded to start wondering how you can recover. Instead, assume that a cyberattack will eventually happen and plan in advance how you'll recover.
Important feature that the backup must have
- **Comprehensive** : Identify every critical server and data store in your organization and make sure it's backed up regularly
- **Up to date** : Always update the data so that the user can't loose hi data of a single day
- **Redundant** : A user should keep multiple copies of the backups each representing a different recovery point. This way if the most recent set of backup doesn't work you can revert to the set.
- **Kept off-site** : If a fire burns down your server room and your backups are kept on a shelf next to the servers, you'll lose the backups too, At that point, you won't be able to restore anything
- **Offline** : To protect against cyberattacks, Human error, physical disaster and hardware failure and etc.
- **Automated** : Don't rely on remembering to run a backup every Friday at the end of the day, You'll forget. Make sure your backup process are automated
- **Monitored** : Monitor your backups regularly to ensure they're working as designed
- **Tested** : Regularly test them by restoring individual files and entire servers
- **Spare computers** : If a cyberattack compromises one of your desktop computers make sure you have a spare or two that you can quickly configure to quickly get the user back to work
- **Emergency disk capacity** : Restore operations often require that you have plenty of spare disk capacity available so that you can move data around
- **Communication** : In the midst of a recovery from a cyberattack, it's vital that you communicate with your users.
## Cybersecurity Frameworks
5 most popular Cybersecurity frameworks are :

| FEATURE/FRAMEWORK      | NIST CSF(2.0)                                                                                                                | ISO/IEC 27001 (ISMS)                                                                       | ISA/IEC 62443 (OT/IACS)                                                                                              | CIS control (v8)                                                                                       | COBIT(2019)                                                                                             |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Primary focus          | Flexible, outcome-driven cybersecurity risk management for all sectors                                                       | Information security Management system (ISMS for all information assets)                   | Cybersecurity for industrial automation and control system (IACS)/ Operations Technology(OT)                         | Prioritized prescriptive technical controls for common cyberattacks                                    | IT governance and management aligning IT with business goal                                             |
| Domain                 | All IT environments, adaptable for OT.                                                                                       | General IT, Corporate IT, Information assets                                               | Industrial Control Systems, SCADA, PLCs, DCS, Critical Infrastructure.                                               | General IT, focusing on common vulnerabilities.                                                        | Enterprise-wide IT, encompassing all IT processes and functions.                                        |
| Key Objectives         | Understanding, managing, and reducing cybersecurity risk.                                                                    | Confidentiality, Integrity, Availability   (CIA) of information                            | Safety, Reliability, Availability, Integrity of physical processes controlled by IACS.                               | Blocking common and dangerous cyberattacks. Basic cyber hygiene.                                       | Value creation from IT, risk optimization, resource optimization, meeting stakeholder needs.            |
| Nature                 | Voluntary Framework for risk management. Not for certification.                                                              | Standard for ISMS certification. Auditable                                                 | Series of standards for IACS security (policies, system, component). Some parts certifiable.                         | Best practices/Guidelines. Not for formal certification (though compliance can be assessed).           | Governance and Management Framework. Not for organization certification (individuals can be certified). |
| Approach               | Flexible, outcome-driven, identifies functions/ categories/ subcategories. Uses Profiles & Tiers.                            | Risk-based, Plan-Do-Check-Act (PDCA) cycle for ISMS. Focuses on what to do                 | Risk-based, detailed technical and process requirements, covers full lifecycle of IACS. Shared responsibility model. | Prescriptive, prioritized "Safeguards" organized into Implementation Groups. Focuses on how to defend. | Principle-based, process-oriented, with design factors for customization. Bridges IT & business.        |
| Target Audience        | All levels: technical staff, security teams, business leaders, executives.                                                   | CISCOs, IT managers, GRC professionals, anyone needing to demonstrate robust info security | OT security engineers, IACS designers, system integrators, asset owners in industrial sectors.                       | Security practitioners, IT staff, small-medium businesses. Practical implementers.                     | Senior IT management, CIOs, Board members, Auditors, Business executives.                               |
| Relationship to Others | High-level, flexible. Often references/points to ISO 27001, CIS Controls, COBIT, etc., for specific guidance.                | Often integrated with NIST or COBIT for broader scope Controls may align with CIS          | Specialized for OT; often used in conjunction with ISO 27001 or NIST CSF for IT-OT convergence.                      | Can serve as a practical starting point, often mapped to NIST CSF or ISO 27001.                        | "Umbrella" framework for IT governance, can integrate ISO 27001, NIST CSF, ITIL, etc.                   |
| Detail Level           | High-level functions and categories, with subcategories being more specific outcomes. References other standards for detail. | High-level management system requirements, with detailed Annex A control                   | Very detailed technical and procedural requirements specific to industrial environments.                             | Highly granular and actionable technical "Safeguards."                                                 | High-level governance and management objectives, with supporting components.                            |

Operational technology (OT) refers to hardware and software that detects or causes a change through the direct monitoring and/or control of industrial equipment, assets, processes, and events.
#### NIST Cybersecurity Framework
Previously The framework is for improving Critical infrastructure. 
The framework was originally intended to apply to critical infrastructure such as the power grid, transportation systems, dams , government agencies and so on.
	For example
	- **Before CSF:** A water utility might have individual departments managing IT and OT security in silos, with no unified view of risk. Backup strategies might be ad-hoc.
	- **With CSF:**
    - They would use the **Identify** function to map all their IT and OT assets, understand dependencies, and assess risks to their water treatment and distribution processes.    
    - The **Protect** function guides them to implement specific controls like network segmentation between IT and OT, multi-factor authentication for control systems, and secure configuration of PLCs.
    - The **Detect** function prompts them to set up continuous monitoring for anomalous behavior in their control networks, not just their corporate network.
	- The **Respond** function leads to the development of detailed incident response plans specific to a control system disruption (e.g., how to manually operate a valve if SCADA is compromised).
	- The **Recover** function ensures they have tested procedures to restore water services rapidly after a cyber event, including recovery of critical data and system configurations.
	- The new **Govern** function helps them establish clear leadership, policies, and supply chain management for both IT and OT cybersecurity.
[[NIST.CSWP.04162018.pdf]]
This is the complete documentation for the cybersecurity framework 
The framework consist of three basic components
#### Framework core 
This section identifies five basic functions of cybersecurity
- **Identify** : You must know in detail exactly what parts of your organization are vulnerable to cyberattack
- **Protect** : You should take specific steps to protect those part of your organization that you've identified as being vulnerable
- **Detect** : This function involves monitoring an your systems and environment so that you know as soon as possible when a cyberattack occurs
- **Respond** : This function help you plan in advance how you'll respond when a cybersecurity incident occurs
- **Recover** : According to the framework you must create multiple backup of the data
**Framework Implementation Tiers** : This section describes four distinct tiers that represent an increasing level of sophistication in cybersecurity practices. As an organization invests more in cybersecurity, it moves up through the tier levels.
**Framework Profile** : This section discusses the use of profiles to indicate which specific outcomes in the framework cores are implemented. you can create a current profile(Your cybersecurity reality today) which documents the cybersecurity practices at your organization and then create a target profile(Your desired cybersecurity goal for the future) to represent where you'd like to be. Then you can device a plan (The steps you'll take to close the gaps between your reality and your goal) to move from current profile to target profile
![[Pasted image 20250618221414.png]]
==REMEMBER==
%% Although the Framework doesn’t prescribe specific solutions, it
does offer a set of links to other cybersecurity frameworks which it calls Informative References. For example, ID.AM-1 includes references to related information found in the CIS Controls, COBIT controls, ISA/IEC standards, and other NIST standards. You can cross-reference these Information References to gain additional insight into each of the subcategories. %%