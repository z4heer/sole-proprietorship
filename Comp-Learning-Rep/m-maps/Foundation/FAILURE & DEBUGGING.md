```markdown id="hw-failure-debug"
# Hardware FAILURE & DEBUGGING

## Common Symptoms
- Server not booting
- Random shutdowns
- Slow system performance
- Disk read/write failures
- Network disconnects
- Overheating alerts

## Root Causes
- Power supply failure
- Faulty RAM or storage
- Cooling system issues
- Damaged motherboard
- Loose cables/connectors
- Hardware aging

## Failure Points
- CPU socket
- RAM modules
- SSD/HDD disks
- Network interface cards
- Power units
- Cooling fans

## Debugging Tools
- BIOS/UEFI diagnostics
- Hardware monitoring tools
- SMART disk utilities
- Vendor diagnostic tools
- Rack management consoles

## Logs & Metrics
- Temperature metrics
- Power consumption
- Disk health status
- Hardware error logs
- Fan speed metrics

## Resolution
- Replace faulty components
- Re-seat cables/modules
- Upgrade cooling
- Restore failed disks
- Failover to backup hardware

## Prevention
- Redundant hardware setup
- Preventive maintenance
- Proper cooling management
- Capacity planning
- Hardware lifecycle upgrades

## Monitoring Indicators
- CPU temperature spikes
- Disk latency/errors
- Memory failure alerts
- Packet loss
- Power instability

## Owner
- Infrastructure teams
- Datacenter operations
- Hardware support engineers

## Consumer Impact
- Application downtime
- Data loss risk
- Performance degradation
- Service outages
```

---

```markdown id="cpu-failure-debug"
# CPU FAILURE & DEBUGGING

## Common Symptoms
- High CPU utilization
- Slow application response
- System freezes
- Process throttling
- Excessive load average

## Root Causes
- Infinite loops
- Heavy queries/computations
- Insufficient CPU capacity
- Thermal throttling
- Poor thread management

## Failure Points
- CPU cores
- Scheduler overload
- Cache bottlenecks
- Virtualization contention

## Debugging Tools
- top / htop
- mpstat
- perf
- vmstat
- Profilers and APM tools

## Logs & Metrics
- CPU utilization %
- Load average
- Context switching
- Process wait times
- Thermal metrics

## Resolution
- Kill runaway processes
- Optimize code/queries
- Increase compute resources
- Scale workloads horizontally
- Tune thread allocation

## Prevention
- Capacity planning
- Performance testing
- Autoscaling policies
- Efficient code optimization

## Monitoring Indicators
- Sustained high CPU %
- Queue/wait spikes
- Increased response latency
- Thermal warnings

## Owner
- Performance engineers
- DevOps/SRE teams
- Infrastructure teams

## Consumer Impact
- Slow applications
- API latency
- Request timeouts
- Reduced throughput
```

---

```markdown id="os-failure-debug"
# Operating System FAILURE & DEBUGGING

## Common Symptoms
- Server crashes
- Memory exhaustion
- Slow boot times
- File system corruption
- Process failures
- Network instability

## Root Causes
- Resource exhaustion
- Driver conflicts
- Misconfiguration
- Kernel panic
- Disk or memory issues

## Failure Points
- Kernel
- Process scheduler
- File system
- Device drivers
- Network stack

## Debugging Tools
- top / ps
- dmesg
- journalctl
- netstat / ss
- system diagnostics tools

## Logs & Metrics
- System logs
- Kernel logs
- Memory usage
- Disk I/O metrics
- Network statistics

## Resolution
- Restart failed services
- Apply configuration fixes
- Patch/update OS
- Clean resource leaks
- Restore corrupted systems

## Prevention
- Patch management
- Configuration standardization
- Backup and recovery
- Resource monitoring
- Security hardening

## Monitoring Indicators
- Memory pressure
- Disk saturation
- Kernel errors
- Service restart frequency
- Network drops

## Owner
- System administrators
- Platform teams
- DevOps/SRE teams

## Consumer Impact
- Service outages
- Slow systems
- Failed deployments
- User access issues
```

---

```markdown id="linux-failure-debug"
# Linux FAILURE & DEBUGGING

## Common Symptoms
- High load average
- SSH inaccessible
- Service crashes
- Disk full errors
- Container failures
- Slow server response

## Root Causes
- Misconfigured services
- Memory leaks
- CPU or disk bottlenecks
- Permission issues
- Network/firewall problems
- Kernel resource exhaustion

## Failure Points
- Linux kernel
- Systemd services
- File systems
- Networking stack
- Package dependencies

## Debugging Tools
- top / htop
- journalctl
- dmesg
- iostat / vmstat
- tcpdump / ss
- systemctl

## Logs & Metrics
- Syslog/journald logs
- CPU and memory usage
- Disk I/O latency
- Network throughput
- Process/service states

## Resolution
- Restart services
- Free system resources
- Fix permissions/firewall
- Tune kernel parameters
- Scale infrastructure

## Prevention
- Monitoring and alerting
- Log rotation management
- Automation and patching
- Security hardening
- Infrastructure testing

## Monitoring Indicators
- Load average spikes
- OOM kill events
- Disk utilization %
- Failed services
- Network packet drops

## Owner
- Linux administrators
- DevOps/SRE teams
- Platform engineers

## Consumer Impact
- API downtime
- Deployment failures
- Application instability
- Reduced system performance
```
