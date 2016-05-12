# ESX-Settings

*###### General*
1. Ensure that the iSCSI LUNs consumed by ESX clients have blockLength=512
2. Set Disk time out (blockingTimeoutSeconds) to 10800
3. MTU should be 9000 for all network ports

*###### Advance Settings (ESX -> Configuration Tab -> Software -> Advance Settings )*
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

*###### Storage Adapter properties (ESX -> Configuration -> Storage adapters -> Properties -> General -> Advanced)*
1. Set MaxOutstandingR2T to 8
2. Set LoginTimeout to 60
3. Disable Delayed ack - Uncheck 

*###### Storage vmotion Setting*

fsr.maxSwitchoverSeconds = 300 

The default (fsr.maxSwitchoverSeconds) timeout value is 100 Seconds. We have to change it to 300 Seconds.

To modify the fsr.maxSwitchoverSeconds option using the vSphere Client:

1. Open vSphere Client and connect to the ESX/ESXi host or to vCenter Server.
2. Locate the virtual machine in the inventory.
3. Power off the virtual machine.
4. Right-click the virtual machine and click Edit Settings.
5. Click the Options tab.
6. Select the Advanced: General section.
7. Click the Configuration Parameters button. Note: The Configuration Parameters button is disabled when the virtual machine is powered on.
8. From the Configuration Parameters window, click Add Row.
9. In the Name field, enter the parameter name: fsr.maxSwitchoverSeconds =300
10. In the Value field, enter the new timeout value in seconds (for example: 150).
11. Click the OK buttons twice to save the configuration change.
12. Power on the virtual machine.
