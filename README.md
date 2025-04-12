## Script: Get Availability Group Database Sync and Join Status (Local Replica)

**Description**:
This script retrieves detailed information about the synchronization status of databases participating in Always On Availability Groups, specifically for the **local replica**. It helps identify whether databases are joined, synchronized, or suspended.

**What It Shows**:
- `AvailabilityGroupName`: The name of the AG
- `ListenerName`: The DNS name of the AG listener
- `DatabaseName`: Name of the participating database
- `SynchronizationState`: 0 = Not Synchronizing, 1 = Synchronizing, 2 = Synchronized
- `IsSuspended`: 1 if the database sync is suspended
- `IsJoined`: 1 if the database is joined to the AG on the current node

**Use Case**:
- Monitor database-level health in Availability Groups
- Troubleshoot sync issues or data movement delays
- Detect suspended or unjoined databases

**Requirements**:
- SQL Server 2012 or later
- Always On must be enabled
- The script must be executed on a node that is part of the AG
- `VIEW SERVER STATE` permission required

**Notes**:
- The results are specific to the **local replica**.
- You can uncomment `PrimaryReplicaServerName` or `LocalReplicaRole` fields for deeper role context.
