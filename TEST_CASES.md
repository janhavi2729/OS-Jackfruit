# Test Cases — OS Jackfruit

## Test Case 1: Engine Startup
Command:
./engine

Expected:
Usage message displayed

Result:
Program prints usage correctly.

---

## Test Case 2: Root Filesystem Setup
Command:
ls

Expected:
rootfs-alpha, rootfs-beta exist

Result:
Root filesystems created successfully.

---

## Test Case 3: Container Shell
Command:
sudo ./engine run alpha rootfs-alpha /bin/sh

Expected:
Shell inside container

Result:
Shell opened successfully with isolated environment.

---

## Test Case 4: CPU Workload
Command:
sudo ./engine run alpha rootfs-alpha /cpu_hog

Expected:
CPU-intensive execution

Result:
cpu_hog ran and exited successfully.

---

## Test Case 5: PID Isolation
Command:
ps (inside container)

Expected:
Only container processes visible

Result:
Minimal processes shown → isolation confirmed.

---

## Test Case 6: Kernel Module Load
Command:
sudo insmod monitor.ko

Expected:
Device created

Result:
/dev/container_monitor exists.

---

## Test Case 7: Kernel Monitoring
Command:
sudo ./engine run alpha rootfs-alpha /cpu_hog
sudo dmesg | tail -20

Expected:
Kernel logs container registration

Result:
[container_monitor] Registering container-alpha observed.
