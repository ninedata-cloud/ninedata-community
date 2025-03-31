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
   docker run -p 9999:9999 --privileged -v /opt/ninedata:/u01 --name ninedata -d swr.cn-east-3.myhuaweicloud.com/ninedata/ninedata:latest
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
