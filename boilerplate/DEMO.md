# Demonstration Steps

1. Navigate to project directory:
   cd ~/OS-Jackfruit/boilerplate

2. Build project:
   make

3. Load kernel module:
   sudo rmmod monitor 2>/dev/null
   sudo insmod monitor.ko

4. Verify device:
   ls /dev/container_monitor

5. Run container shell:
   sudo ./engine run alpha rootfs-alpha /bin/sh

6. Inside container:
   ls /
   ps
   exit

7. Run CPU workload:
   sudo ./engine run alpha rootfs-alpha /cpu_hog

8. View kernel logs:
   sudo dmesg | tail -20
