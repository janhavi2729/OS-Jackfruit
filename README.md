# OS Jackfruit — Lightweight Container Runtime

## Overview
This project implements a lightweight container runtime in C with kernel-level monitoring.

## Features
- Container execution using clone()
- PID namespace isolation
- Filesystem isolation using chroot
- Kernel module for monitoring
- User-kernel communication using ioctl

## Architecture
- engine.c → user-space runtime
- monitor.c → kernel module
- monitor_ioctl.h → ioctl interface

## Execution Flow
1. User runs container
2. clone() creates isolated process
3. chroot() isolates filesystem
4. Workload executes
5. PID sent to kernel module
6. Kernel logs monitoring data

## Test Cases
See TEST_CASES.md

## Screenshots
(Add screenshots here)

## Conclusion
Successfully implemented container runtime with kernel monitoring.
