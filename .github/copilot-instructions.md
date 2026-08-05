## Copilot instructions for E-Series storage systems documentation

### Repository overview
Product: E-Series storage systems

NetApp *E-Series* documentation in this repository covers hardware installation, SAN host configuration, maintenance, controller/software upgrades, and SANtricity management integrations for E-Series and EF-Series storage arrays. The content also includes component-specific procedures for API, vCenter, remote import, and cloud backup integrations.

### Repository structure
- `_include/` – Reusable include files shared across pages.
- `cloud-connector/` – SANtricity Cloud Connector overview and backup/restore guidance for S3-compatible and AltaVault targets.
- `config-linux/` – Linux express host configuration workflows for Fibre Channel, iSCSI, SAS, and InfiniBand-based paths.
- `config-vmware/` – VMware express host configuration workflow for connecting E-Series storage to vSphere environments.
- `config-windows/` – Windows express host configuration workflow for connecting E-Series storage to Windows hosts.
- `getting-started/` – Core concepts, terminology, hardware/software overviews, and quick-start task flow.
- `install-hw-cabinet/` – Installation procedures for the 3040 40U cabinet.
- `install-hw-cabling/` – Cabling requirements and procedures for host, shelf, Ethernet, and power connections.
- `install-hw-e2800-e5700/` – Installation and setup workflows for E2800 and E5700 systems.
- `install-hw-e4000/` – Installation and setup workflows for E4000 systems.
- `install-hw-ef50-ef80/` – Installation and setup workflows for EF50 and EF80 systems.
- `install-hw-ef600/` – Installation and setup workflows for EF300/EF600 platform families.
- `maintenance-e2800/` – Hardware replacement and maintenance procedures for E2800 systems.
- `maintenance-e4000/` – Hardware replacement and maintenance procedures for E4000 systems.
- `maintenance-e5700/` – Hardware replacement and maintenance procedures for E5700 systems.
- `maintenance-ef50-ef80/` – Hardware replacement and maintenance procedures for EF50 and EF80 systems.
- `maintenance-ef600/` – Hardware replacement and maintenance procedures for EF300 and EF600 systems.
- `media/` – Shared images and media assets referenced by AsciiDoc content.
- `redirect/` – Redirect mapping content for moved or renamed pages.
- `remote-storage-volumes/` – SANtricity Remote Storage Volumes feature documentation for importing data from remote storage into local E-Series volumes.
- `upgrade-controllers/` – Controller replacement workflows used to upgrade array controller platforms.
- `upgrade-santricity/` – SANtricity OS and related firmware upgrade workflows.
- `vcenter-plugin/` – SANtricity Storage Plugin for vCenter installation, discovery, provisioning, and operation topics.
- `web-services-proxy/` – SANtricity Web Services Proxy and REST API installation/configuration documentation.

### Product-specific context
**Architecture and components:**
- An *E-Series storage array* is composed of shelves, controllers, drives, firmware, and SANtricity software.
- *SANtricity System Manager* is embedded on each controller and manages a single storage array through the controller IP address.
- *SANtricity Unified Manager* runs with *Web Services Proxy* on a management server and provides centralized multi-array management and batch operations.
- *Web Services Proxy* exposes REST APIs for managing newer and legacy E-Series arrays and underpins Unified Manager operations.
- The *SANtricity Storage Plugin for vCenter* integrates E-Series management into VMware vSphere Client and can launch System Manager for per-array tasks.
- *Remote Storage Volumes* connects a remote storage system and an E-Series system to import remote block data directly into local E-Series volumes.
- *SANtricity Cloud Connector* is a host-based Linux application for block- and file-based backup/restore of E-Series volumes to S3-compatible or AltaVault targets.

**Key concepts:**
- A *controller* runs array control logic and storage management functions; arrays can be *simplex* (single controller) or *duplex* (dual controller).
- A *pool* is a logical grouping of drives used to create host-accessible *volumes*.
- A *workload* is an application-oriented storage object used to group volumes with similar characteristics.
- A *snapshot* is a point-in-time logical copy of volume data used for rollback and data protection workflows.
- A *controller shelf* contains controllers and drives, while a *drive shelf* adds expansion capacity through I/O modules and drives.

**Naming conventions and terminology:**
- Use *SANtricity* names exactly: *System Manager*, *Unified Manager*, *Web Services Proxy*, and *Storage Plugin for vCenter*.
- *HIC* means *host interface card*; *IOM* means shelf *input/output module*.
- *RTV* refers to *Remote Storage Volumes*.
- *IB* refers to *InfiniBand*; *RoCE* refers to *RDMA over Converged Ethernet*.
- *IOPS* means input/output operations per second and is used in performance-related topics.

### Typical user workflows
**Initial deployment:** Select hardware workflow → Install shelf/cabinet hardware → Cable host/shelf/network links → Power on and complete setup → Access SANtricity management interface

**Host access configuration:** Choose host OS guide (Linux/VMware/Windows) → Verify host prerequisites and connectivity → Configure host-side multipath/network settings → Create storage and host mappings → Verify host storage access

**Centralized multi-array management:** Install Web Services Proxy with Unified Manager → Discover arrays on the network → Group arrays and import shared settings → Run batch operations (for example upgrades) → Launch per-array System Manager as needed

**Remote data migration:** Review Remote Storage Volumes requirements → Configure remote and local system connectivity → Start remote import to local E-Series volume → Monitor import and validate migrated data
