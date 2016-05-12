# ESX-Settings

#### General
1. Ensure that the iSCSI LUNs consumed by ESX clients have blockLength=512
2. Set Disk time out (blockingTimeoutSeconds) to 10800
3. MTU should be 9000 for all network ports

###### Advance Settings (ESX -> Configuration Tab -> Software -> Advance Settings )
1. Set NFS.MaxVolumes to 256
2. Set Net.TcpipHeapMax to 128
3. Set Net.TcpipHeapSize to 32
4. Set Migrate.CptCacheMaxSizeMB to 512
5. Set Migrate.DiskiOpsMaxRetries to 100
6. Set Migrate.MigrateCpuMinPctDefault to 300
7. Set Migrate.MigrateCpuPctPerGb to 30
8. Set Migrate.NetTimeout to 1800
9. Set Migrate.VASpaceReserveCount to 24
10. Set Migrate.VMotionStreamHelpers to 8

###### Storage Adapter properties (ESX -> Configuration -> Storage adapters -> Properties -> General -> Advanced)
1. Set MaxOutstandingR2T to 8
2. Set LoginTimeout to 60
3. Disable Delayed ack - Uncheck 
