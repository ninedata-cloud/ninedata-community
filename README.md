[中文文档](README_CN.md) | [English Documentation](README.md)

# NineData Community Edition

This article provides a detailed introduction to NineData Community Edition, including its product positioning and a multi-dimensional comparison with the Enterprise Edition, helping you quickly understand the Community Edition.

### What is NineData Community Edition?

NineData Community Edition is a **permanently free**, one-click-install data management solution launched by Jiuzhang Arithmetic, designed for developers, startups, educational institutions, and individual users. It includes three core functionalities of NineData: **Database DevOps**, **Data Replication**, and **Database Comparison**.

- **Database DevOps**: Offers robust features such as data source management, data querying, SQL standardization, SQL auditing, and approval workflows. It enables users to efficiently manage multi-environment database tasks, accelerating enterprise digital transformation.
- **Data Replication**: Supports offline and real-time replication across diverse homogeneous/heterogeneous data sources. Ideal for scenarios like data migration, database scaling, version upgrades, cross-region disaster recovery, multi-active architectures, and data lake/warehouse integration.
- **Database Comparison**: Compares content consistency between two data sources. If inconsistencies are detected, it automatically generates SQL scripts to synchronize data and schemas.

NineData Community Edition is a **fully offline, locally deployed solution** that requires no connection to cloud services or the NineData website. All data and operations remain 100% within your local environment, making it ideal for internal networks without external access, small businesses, personal projects, or learning/testing scenarios.

For deployment, NineData Community Edition leverages Docker technology. Users can install it locally with a single command, enabling rapid setup regardless of technical expertise.

### Core Value Propositions

✅ **Permanently Free & User-Friendly**
Free to use forever, deployable in 10 minutes, with fully visual operations.

✅ **Supports Cloud VM or On-Premises Deployment**
Deployable on cloud VMs or private networks to meet data compliance requirements for sensitive operations.

✅ **Secure and Efficient Data Management**
Built on 15 years of expertise, it delivers a professional Database DevOps solution to enhance collaboration between developers and DBAs while ensuring data security.

✅ **High-Performance Real-Time Data Sync**
Powered by self-developed CDC technology, it handles database migration, synchronization, and disaster recovery, supporting **tens of thousands of TPS** in real-time replication.

### Community Edition vs. Enterprise Edition (formerly NineData Dedicated Cluster)

| **Comparison Criteria**   | **Community Edition**           | **Enterprise Edition**                   |
| :------------------------ | :------------------------------ | :--------------------------------------- |
| **Core Audience**         | Developers/Startups/Individuals | Medium/Large Enterprises & Production    |
| **Deployment**            | Docker Single-Node              | Docker Single-Node/Distributed Cluster   |
| **Database DevOps**       | 10 Data Sources                 | Unlimited (Scalable via Licensing)       |
| **Data Replication**      | 10 Tasks (2 Incremental Tasks)  | Unlimited (Scalable via Licensing)       |
| **Database Comparison**   | Up to 10 Tasks                  | Unlimited                                |
| **Deployment Complexity** | ⭐⭐⭐⭐⭐ Single-Command            | ⭐⭐⭐⭐ Scalable Nodes/Configurations       |
| **Resource Usage**        | Single Machine                  | Cluster (Cross-Region DR & Multi-Active) |
| **Support**               | Docs + WeChat Group             | 24/7 Dedicated Support + SLA             |
| **Pricing**               | Free Forever                    | Pay-as-You-Go                            |

### Deployment Guide

**Prerequisites**

- Docker installed on the server.
- Minimum server specs: **4-core CPU, 16GB RAM, 200GB disk space**.
- The CPU is based on the **Intel x86_64** architecture.

**Steps**

1. Log into the server’s CLI and run:

   ```
   docker run -p 9999:9999 --privileged -v /opt/ninedata:/u01 --name ninedata -d ninedata/ninedata:latest
   ```

   **Parameter Details**

   - `-p 9999:9999`: Maps the container’s port 9999 to the server’s port 9999 for browser access.
   - `--privileged`: Grants privileged system access to the container.
   - `-v /opt/ninedata:/u01`: Mounts the server’s `/opt/ninedata` to the container’s `/u01` for data storage.
   - `--name ninedata`: Assigns a container name (customizable).
   - `-d [image]`: Specifies the NineData image.

   **Regional Mirrors (Optional)**

   - North China-Beijing: `swr.cn-north-4.myhuaweicloud.com/ninedata/ninedata:latest`
   - East China-Shanghai: `swr.cn-east-3.myhuaweicloud.com/ninedata/ninedata:latest`
   - South China-Guangzhou: `swr.cn-south-1.myhuaweicloud.com/ninedata/ninedata:latest`
   - Docker Hub: `ninedata/ninedata:latest`

2. After starting the container, NineData initializes automatically (~5–10 minutes). Monitor progress with `docker logs -f ninedata`.  Once the startup message appears, access NineData via `http://<server_ip>:9999`. 

   ![image-20250310171459303](https://docs.ninedata.cloud/en/assets/images/image-20250310171459303-665e43ce5b19cdebe5096822db6132ba.png)

3. Log in to the NineData console using the default credentials `admin/admin`, and change the password immediately upon first login.

   ![image-20250310171539071](https://docs.ninedata.cloud/en/assets/images/image-20250310171539071-217f967f9d5fe319957c3ea977bcbeb1.png)

### Comprehensive Comparison of NineData Community Edition with Mainstream Tools
**Database DevOps**
<div class='table_detail_wrapper'><table><thead>
  <tr>
    <th colspan="2">Comparison Items</th>
    <th>NineData Community Edition</th>
    <th>Archery</th>
    <th>Yearning</th>
    <th>Navicat</th>
    <th>Flyway</th>
    <th>Liquibase</th>
  </tr></thead>
<tbody>
  <tr>
    <td rowspan="4">Basic Capabilities</td>
    <td>Update and Iteration Frequency</td>
    <td>High (Continuous delivery, weekly iteration)</td>
    <td>Medium (Quarterly updates, driven by the open-source community)</td>
    <td>Medium (Irregular updates, dependent on community contributions)</td>
    <td>Medium (Annual major versions, quarterly minor updates)</td>
    <td>Medium (Regular feature enhancements, about once every six months)</td>
    <td>Medium (Regular maintenance, quarterly updates)</td>
  </tr>
  <tr>
    <td>Deployment Mode</td>
    <td>Docker Deployment</td>
    <td>Docker Deployment</td>
    <td>Docker Deployment</td>
    <td>Desktop Application</td>
    <td>CLI Integrated with Java</td>
    <td>CLI Integrated with Java</td>
  </tr>
  <tr>
    <td>Supported Data Sources</td>
    <td>Domestic databases, data warehouses, multi-cloud databases (such as AWS, Alibaba Cloud, etc.), MySQL, PG, Oracle, SQL Server, Db2, etc.</td>
    <td>MySQL, PG, Redis, etc.</td>
    <td>MySQL, PG</td>
    <td>MySQL, PG, Oracle, SQL Server, etc.</td>
    <td>MySQL, PG, Oracle, and other mainstream databases</td>
    <td>Mainstream databases (similar to Flyway)</td>
  </tr>
  <tr>
    <td>Login Method</td>
    <td>Account password/third-party login/SSO(LDAP)</td>
    <td>Web account/LDAP/OAuth</td>
    <td>Web account/LDAP</td>
    <td>Local account/License</td>
    <td>No (Command line)</td>
    <td>No (Command line/Code)</td>
  </tr>
  <tr>
    <td rowspan="5">SQL IDE</td>
    <td>Supported Languages</td>
    <td>Chinese and English</td>
    <td>Primarily Chinese</td>
    <td>Chinese</td>
    <td>Multiple languages</td>
    <td>English</td>
    <td>English</td>
  </tr>
  <tr>
    <td>SQL Window</td>
    <td>Supported (Strong)</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported (Strong)</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Object Visual Management</td>
    <td>Supported</td>
    <td>Partially supported (table structure)</td>
    <td>Limited</td>
    <td>Supported (Graphical)</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Query Result Set Operations</td>
    <td>Export, Edit</td>
    <td>Export, Edit</td>
    <td>Export</td>
    <td>Export, Edit, Charts</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Session Isolation</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="9">SQL Review and Release</td>
    <td>SQL Change Release</td>
    <td>Work Order + Automated Process</td>
    <td>Work Order Approval + Execution</td>
    <td>Work Order Approval</td>
    <td>Direct Execution</td>
    <td>Direct Execution of Migration Scripts</td>
    <td>Direct Execution of Scripts</td>
  </tr>
  <tr>
    <td>Change Automatic Backup</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Manual Backup</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Approval Process</td>
    <td>Multi-level approval, can be connected to external approval processes</td>
    <td>Multi-level approval</td>
    <td>Simple approval</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Online DDL</td>
    <td>Natively Supported</td>
    <td>Dependent on tools such as PT-OSC</td>
    <td>Dependent on external tools</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Online DML</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Built-in SQL Standards</td>
    <td>200+ built-in rules for various database types / custom</td>
    <td>Some rules for MySQL</td>
    <td>Some rules for MySQL</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Mobile Approval</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Release Process Orchestration</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>SQL Code Review</td>
    <td>Strong (Automated Review)</td>
    <td>Average (Custom Rules)</td>
    <td>Average (Built-in Rules)</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="4">Data Security</td>
    <td>Sensitive Data Protection</td>
    <td>Intelligent data classification and grading, complete data desensitization + encryption</td>
    <td>Support manual settings, but can be easily bypassed</td>
    <td>Support manual settings, but can be easily bypassed</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Permission Authorization Mode</td>
    <td>RBAC + ABAC, administrator authorization + active application</td>
    <td>RBAC, administrator authorization + active application</td>
    <td>RBAC, administrator authorization</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Permission Model</td>
    <td>Fine-grained permissions (database/table/sensitive column/module/operation)</td>
    <td>Project-level isolation</td>
    <td>User-level permissions</td>
    <td>Local permissions</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Operation Audit</td>
    <td>Full-link audit</td>
    <td>Complete logs</td>
    <td>Basic logs</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="5">Advanced Data Processing</td>
    <td>Data Import</td>
    <td>Multi-format import, syntax-level controllable</td>
    <td>Support for CSV/SQL</td>
    <td>Support for CSV</td>
    <td>Multiple formats (Excel, CSV, etc.)</td>
    <td>Through migration scripts</td>
    <td>Through scripts</td>
  </tr>
  <tr>
    <td>Data Export</td>
    <td>Multi-format export, file encryption, watermark protection</td>
    <td>Support for CSV</td>
    <td>Support for CSV</td>
    <td>Multiple formats export</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Data Archiving and Cleaning</td>
    <td>Automatic archiving (MySQL, PG)</td>
    <td>Manual (MySQL)</td>
    <td>X</td>
    <td>Manual</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Data Tracking and Rollback</td>
    <td>Automatic parsing of Binlog to generate in reverse</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Data Generation</td>
    <td>Supported, simulation template customization</td>
    <td>X</td>
    <td>X</td>
    <td>Support for test data generation</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="2">Performance Diagnosis</td>
    <td>Slow SQL Performance Analysis</td>
    <td>In-depth analysis + optimization suggestions (MySQL, PG, Oracle, Db2)</td>
    <td>Support (MySQL)</td>
    <td></td>
    <td>Basic analysis</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Session Management</td>
    <td>View/Kill sessions</td>
    <td>View/Kill sessions</td>
    <td>View sessions</td>
    <td>View/Kill sessions</td>
    <td>X</td>
    <td>X</td>
  </tr>
  </tbody></table></div>

**Data Replication**
  <div class='table_detail_wrapper'><table><thead>
  <tr>
    <th colspan="2">Comparison Items</th>
    <th>NineData</th>
    <th>Canal</th>
    <th>DataX</th>
    <th>FlinkCDC</th>
  </tr></thead>
<tbody>
  <tr>
    <td rowspan="4">Basic Functions</td>
    <td>Types of Supported Data Sources</td>
    <td>60+</td>
    <td>1</td>
    <td>30</td>
    <td>10+</td>
  </tr>
  <tr>
    <td>Visual Data Source Configuration Management</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>User Management</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Permission Management</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="13">Core Functions</td>
    <td>Table Structure Migration</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Non-table Object Migration</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Full Data Migration</td>
    <td>Supported</td>
    <td>Partially supported (large tables cannot be successfully migrated)</td>
    <td>Supported</td>
    <td>Supported</td>
  </tr>
  <tr>
    <td>Incremental Data Synchronization (DML)</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>X</td>
    <td>Supported</td>
  </tr>
  <tr>
    <td>Incremental Structure Synchronization (DDL)</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>Only supports ADD Column</td>
  </tr>
  <tr>
    <td>Data Filtering</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
  </tr>
  <tr>
    <td>Object Name Mapping</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
  </tr>
  <tr>
    <td>Data Transformation Processing</td>
    <td>Supported</td>
    <td>X</td>
    <td>Supported</td>
    <td>Supported</td>
  </tr>
  <tr>
    <td>Structure Comparison</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Full Data Comparison</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Incremental Data Comparison</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Modify Synchronization Objects</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Visual Task Configuration and Management</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>Basic</td>
  </tr>
  <tr>
    <td rowspan="6">Task Management</td>
    <td>Task High Availability and Automatic Disaster Recovery (task level, server level)</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>Supported</td>
  </tr>
  <tr>
    <td>Task Pause and Resume</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
    <td>Supported</td>
  </tr>
  <tr>
    <td>Task Throttling</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alerts</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Visual Monitoring</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Data SQL Query Window</td>
    <td>Supported</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
</tbody></table></div>
