# Test Cases

## Test Case 1: Build System

**Command:**

make


**Expected Output:**
Compilation successful or "Nothing to be done for 'all'".

**Result:**
Build completed successfully.

---

## Test Case 2: Kernel Module Loading

**Command:**

sudo insmod monitor.ko
ls /dev/container_monitor


**Expected Output:**
Device file `/dev/container_monitor` exists.

**Result:**
Kernel module loaded and device created successfully.

---

## Test Case 3: Container Shell Execution

**Command:**

sudo ./engine run alpha rootfs-alpha /bin/sh


**Expected Output:**
Shell opens inside container.

**Result:**
Container shell launched successfully.

---

## Test Case 4: PID Namespace Isolation

**Command (inside container):**

ps


**Expected Output:**
Minimal processes visible.

**Result:**
PID isolation verified.

---

## Test Case 5: CPU Workload Execution

**Command:**

sudo ./engine run alpha rootfs-alpha /cpu_hog


**Expected Output:**
cpu_hog execution logs.

**Result:**
Process executed successfully inside container.

---

## Test Case 6: Kernel Monitoring

**Command:**

sudo dmesg | tail -20


**Expected Output:**
Kernel logs showing container registration.

**Result:**
Kernel module successfully receives and logs container data.
