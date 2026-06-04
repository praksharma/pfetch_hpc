TODO: Improve HPC-specific information

[ ] Fix CPU core detection
    - Current output shows "cores 1"
    - Use `nproc` or parse `lscpu`
    - Display total logical CPUs
    - Optionally display physical cores and sockets
    - Example:
      cores 128 (64c x 2 sockets)

[ ] Improve CPU information
    - Remove redundant "64-Core Processor" text if cores are displayed separately
    - Example:
      cpu 2x AMD EPYC 7763

[ ] Add GPU memory information
    - Query memory via nvidia-smi
    - Example:
      gpu     1x NVIDIA A100-SXM4
      gpu_mem 80 GB

[ ] Detect allocated GPUs vs installed GPUs
    - Respect CUDA_VISIBLE_DEVICES
    - Show both if possible
    - Example:
      gpu 1/4 NVIDIA A100-SXM4-80GB

[ ] Improve SLURM information formatting
    - Current line is too long
    - Split into multiple entries:
      job      30074450
      queue    ukaea-amp
      account  ukaea-ap002-gpu
      node     gpu-q-49

[ ] Add SLURM runtime
    - Show how long current job has been running
    - Use SLURM_JOB_ID and squeue

[ ] Add load average
    - Read from /proc/loadavg
    - Example:
      load 24.1 23.8 22.7

[ ] Add disk usage
    - Show home filesystem usage
    - Example:
      disk 2.3T / 7.8T

[ ] Add network information
    - Show IB/Ethernet interface
    - Example:
      net infiniband

[ ] Add hostname clarification
    - When inside SLURM allocation, prefer compute node
    - Avoid showing login-q-1 in title while node says gpu-q-49

[ ] Add HPC mode
    - Detect SLURM_JOB_ID
    - Automatically switch to HPC-oriented layout

[ ] Add fallback handling
    - Gracefully skip fields when commands are unavailable
    - Keep script POSIX-compatible where possible

[ ] Review alignment
    - Long SLURM fields currently overflow
    - Ensure columns remain aligned

[ ] Test on:
      - login node
      - GPU node
      - CPU node
      - interactive SLURM job
      - batch SLURM job
