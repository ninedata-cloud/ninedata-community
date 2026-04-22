# NineData Community Edition

Open-source, self-hosted platform for database change management, data replication, and database comparison.

[中文文档](README_CN.md) | [English Documentation](README.md)

NineData Community Edition is built for teams that need to manage databases and data movement inside their own environment. It combines database change workflows, replication tasks, and consistency verification in one workspace, without requiring a connection to NineData cloud services.

## Why Teams Use NineData

- Self-hosted by default. Run NineData in a private network or controlled environment and keep operations, metadata, and access paths under your own control.
- More than a SQL workflow tool. NineData combines database change management, data replication, and post-migration validation in one product.
- Designed for mixed data stacks. Manage relational databases together with analytical engines, search systems, message queues, graph databases, and time-series platforms.
- Practical for engineering and DBA collaboration. Use approvals, review rules, audits, and visual task management instead of assembling multiple point tools.

## Three Product Areas

### Database Change Management

- Centralized data source management and database access
- SQL review policies and approval workflows
- Controlled schema and data changes with audit trails
- Online DDL and DML operations for supported engines
- Query analysis, session management, and release orchestration

### Data Replication

- Full and incremental replication for selected homogeneous and heterogeneous scenarios
- Visual task configuration, monitoring, throttling, pause, and resume
- Support for migration, synchronization, disaster recovery, and cross-environment delivery workflows

### Database Comparison

- Compare database structures and data between source and target systems
- Identify inconsistencies after migration or ongoing replication
- Generate synchronization SQL when differences are detected

## Typical Scenarios

- Standardize how development and DBA teams submit, review, approve, and execute database changes
- Migrate or synchronize data across environments, versions, regions, or heterogeneous systems
- Verify schema and data consistency after migration, synchronization, or upgrade activities
- Provide one operational console for mixed data infrastructure in internal or regulated environments

## Deploy in Minutes

For a quick evaluation, start NineData with Docker:

```bash
docker run -p 9999:9999 \
  --privileged \
  -v /opt/ninedata:/u01 \
  --name ninedata \
  -d swr.cn-east-3.myhuaweicloud.com/ninedata/ninedata:latest
```

Alternative image:

```bash
docker run -p 9999:9999 \
  --privileged \
  -v /opt/ninedata:/u01 \
  --name ninedata \
  -d ninedata/ninedata:latest
```

After the container starts:

1. Wait about 5 to 10 minutes for initialization.
2. Open `http://<your-host>:9999`.
3. Sign in with the default account `admin/admin`.
4. Change the default password after the first login.

Regional mirror examples:

- `swr.cn-north-4.myhuaweicloud.com/ninedata/ninedata:latest`
- `swr.cn-east-3.myhuaweicloud.com/ninedata/ninedata:latest`
- `swr.cn-south-1.myhuaweicloud.com/ninedata/ninedata:latest`
- `ninedata/ninedata:latest`



## Deployment Notes

NineData Community Edition supports:

- Docker-based deployment for fast evaluation and small-team adoption
- Self-hosted and private-network environments
- External MySQL MetaDB for centralized metadata management
- Upgrade guidance and release notes for ongoing maintenance

Start here:

- [Deploy NineData Community Edition](https://docs.ninedata.cloud/en/community_edition/deploy_ninedata/)
- [Use an External MetaDB](https://docs.ninedata.cloud/en/community_edition/external_metadb/)
- [Upgrade NineData Community Edition](https://docs.ninedata.cloud/en/community_edition/upgrade_ninedata/)
- [Community Release Notes](https://docs.ninedata.cloud/en/release_notes/community/)

## Community Edition

NineData Community Edition is permanently free and intended for developers, startups, labs, educational environments, and teams evaluating self-hosted database operations workflows. It provides a practical entry point for using NineData locally or in small to mid-sized private deployments.

If you need larger-scale deployment models or broader enterprise modules, see the commercial product information on the [NineData website](https://www.ninedata.cloud).

## Contributing

Issues, bug reports, and improvement suggestions are welcome. For larger changes, please open an issue first so the scope and direction can be aligned before implementation.
