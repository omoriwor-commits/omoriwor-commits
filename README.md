# Rotimi Omoriwo

**Oracle Database Engineer** · GoldenGate · Data Guard · RAC/ASM · RMAN · Linux · Python/Bash

I build and run Oracle database environments in my own lab: replication, high availability, backup and recovery, and the scripts that check them. Every project here was built, broken and fixed by me, and I write down what happened, including the failures.

## Featured work

### One-to-many heterogeneous replication — Oracle 19c → Oracle 26ai and SQL Server 2022
A Data Guard–protected Oracle 19c primary feeds two targets through GoldenGate 26ai Microservices: an Oracle 26ai PDB (integrated Replicat) and SQL Server 2022 (distribution path over a locked-down SSH tunnel, then a nonintegrated Replicat). I committed INSERT, UPDATE and DELETE on the source and confirmed each change at both targets, then confirmed the final state on the physical standby.

[Runbook](https://github.com/omoriwor-commits/oracle-db-platform-automation/blob/main/GoldenGate/runbooks/oracle19c-dataguard-to-oracle26ai-and-sqlserver2022.md) · [Incident register](https://github.com/omoriwor-commits/oracle-db-platform-automation/blob/main/Oracle-Database-Platform-Automation/incident-reports/2026-11-18-21-goldengate-mssql-implementation.md) · [Validation record](https://github.com/omoriwor-commits/oracle-db-platform-automation/blob/main/Oracle-Database-Platform-Automation/validation/2026-11-21-one-to-many-cdc-evidence.md)

### Health-check automation for RAC and Data Guard
- [`rac_health_check.py`](https://github.com/omoriwor-commits/enterprise-multicloud-database-platform-lab/blob/main/scripts/oracle-rac/rac_health_check.py) collects cluster, ASM and database checks on a two-node 26ai RAC. Live-tested on my cluster, with a unit test suite.
- [`dataguard_health_check.sh`](https://github.com/omoriwor-commits/enterprise-multicloud-database-platform-lab/blob/main/scripts/dataguard/dataguard_health_check.sh) detects the database role and reports redo transport, apply lag, archive gaps and broker status, with regression tests for failure cases.

### Incident reports
I keep a written record when something breaks: what I saw, how I found the cause, what I changed and what is still open. Examples: [GoldenGate Extract/Replicat startup failure](https://github.com/omoriwor-commits/oracle-db-platform-automation/blob/main/Oracle-Database-Platform-Automation/incident-reports/2026-11-14-17-goldengate-ext19c-rep26ai-startup-failure.md) · [RAC node 2 root-script freeze](https://github.com/omoriwor-commits/oracle-db-platform-automation/blob/main/Oracle-Database-Platform-Automation/incident-reports/2026-10-18-rac26-node2-root-script-vm-freeze.md)

## More projects

| Project | What it covers |
|---|---|
| [Oracle Database Platform Automation](https://github.com/omoriwor-commits/oracle-db-platform-automation) | My main hub: GoldenGate, RAC, Data Guard, RMAN runbooks and scripts |
| [Enterprise Data Platform Labs](https://github.com/omoriwor-commits/enterprise-data-platform-labs) | Oracle 19c → 26ai upgrade and on-prem → OCI migration with GoldenGate, RMAN and Data Pump |
| [Enterprise Multi-Cloud Database Platform Lab](https://github.com/omoriwor-commits/enterprise-multicloud-database-platform-lab) | OCI Oracle 26ai → Azure SQL Server 2022 over a private VPN/BGP link (cloud environment since retired) |
| [NGINX DevOps Project](https://github.com/omoriwor-commits/nginx-devops-project) | Docker, GitHub Actions and Kubernetes delivery |

## How I work

I find the failing layer before I change anything, make one controlled change at a time, and check real data, not just a green status. Repositories run CI checks and secret scanning on every pull request.

All projects are self-built lab environments, not employer production systems.

## Contact

[LinkedIn](https://www.linkedin.com/in/omoriwo/)