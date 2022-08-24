# MISP `security-playbook` Object Template - Workbench

**NOTE: The AUTHORITATIVE JSON schema of the object template is: https://github.com/MISP/misp-objects/blob/main/objects/security-playbook/definition.json**
<br></br>

MISP `security-playbook` objects are used to characterize (describe the properties and the scope of a playbook), manage, store, and share cybersecurity playbooks/orchestration workflows and can also integrate with Cyber Threat Intelligence (CTI) to provide additional context.

This repository is the workbench that the fovea research team used to design the `security-playbook` object template for MISP (https://www.misp-project.org/objects.html#_security_playbook).

The table below represents version 3 of the security-playbook object.

| Attribute Name | Data Type | Description |
| :--- | :--- |:--- |
| **playbook-id** (required)| `text` | A value that uniquely identifies the playbook. If the playbook itself embeds an identifier then the playbook-id SHOULD use the same identifier (value). If not, the producer MAY generate a unique identifier for the playbook |
| **description** (optional)| `text` | An explanation, details, and more context about what this playbook does and tries to accomplish. |
| **revoked** (optional)| `boolean` | A boolean that identifies if the playbook is no longer valid (revoked). |
| **playbook-creation-time** (optional)| `datetime` | The date and time at which the playbook was originally created. |
| **playbook-modification-time** (optional)| `datetime` | The date and time at which the playbook was last modified. |
| **playbook-valid-from** (optional)| `datetime` | The date and time from which the playbook is considered valid and the steps that it contains can be executed. |
| **playbook-valid-until** (optional)| `datetime` | The date and time from which the playbook should no longer be considered a valid playbook to be executed. |
| **playbook-creator** (optional)| `text` | The entity that created the playbook. It can be a natural person or an organization. It may be represented using a unique identifier that identifies the creator. |
| **labels** (optional)| `text` | Labels for this playbook (e.g., adversary persona names, associated groups, malware family/variant/name that this playbook is related to). Another option is to use MISP tags, taxonomies, and galaxies. |
| **organization-type** (optional)| `text` | The type of organization that the playbook is intended for. This can be an industry sector. Another option is to use MISP tags, taxonomies, and galaxies.|
| **playbook-standard** (optional)| `text` | The standard/format/notation the playbook conforms to (e.g., CACAO, BPMN). |
| **playbook-abstraction** (optional)| `text` | The playbook’s level of abstraction (with regards to consumption). Listed options: `[template, executable]` |
| **playbook-type** (optional)| `text` | The security-related functions the playbook supports. A playbook may account for multiple types (e.g., detection and investigation). The listed options are based on the CACAO standard and NIST SP 800-61 rev2. Another option is to use MISP tags, taxonomies, and galaxies. Listed options: `[notification, detection, investigation, prevention, mitigation, remediation, analysis, containment, eradication, recovery, attack]` |
| **playbook-impact** (optional)| `text` | From 0 to 100, a value representing the impact the playbook has on the organization. A value of 0 means specifically undefined. Impact values range from 1, the lowest impact, to a value of 100, the highest. For example, a purely investigative playbook that is non-invasive could have a low impact value of 1. In contrast, a playbook that performs changes such as adding rules into a firewall should have a higher impact value. |
| **playbook-severity** (optional)| `text` | From 0 to 100, a value representing the seriousness of the conditions that this playbook addresses. A value of 0 means specifically undefined. Severity values range from 1, the lowest severity, to a value of 100, the highest. |
| **playbook-priority** (optional)| `text` | From 0 to 100, a value representing the priority of this playbook relative to other defined playbooks. A value of 0 means specifically undefined. Priority values range from 1, the highest priority, to a value of 100, the lowest. |
| **playbook-file** (requiredOneOf)| `attachment` | The entire playbook file/document in its native format (e.g., CACAO JSON or BPMN). |
| **playbook-base64** (requiredOneOf)| `text` | The entire playbook encoded in base64. |

---

### Maintainer 
* Vasileios Mavroeidis [Github handle: @Vasileios-Mavroeidis], [LinkedIn](https://www.linkedin.com/in/vasileiosmavroeidis)
