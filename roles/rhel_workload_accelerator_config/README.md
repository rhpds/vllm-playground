# rhel_workload_accelerator_config

Configures RHEL 10 servers with GPU/accelerator support for AI workloads.

## What It Does

- Enables CodeReady Builder and EPEL repositories
- Installs NVIDIA drivers (DKMS-based)
- Installs nvidia-smi and NVIDIA container toolkit
- Generates CDI configuration for rootless container GPU access
- Reboots and verifies GPU functionality

## Requirements

- RHEL 10
- NVIDIA GPU
- Valid Red Hat subscription

## Usage

```yaml
- hosts: gpu_servers
  vars:
    ACTION: provision
    rhel_workload_accelerator_config_type: nvidia
  roles:
    - rhel_workload_accelerator_config
```

## Variables

See [defaults/main.yml](defaults/main.yml) for all configurable variables.

## Supported Accelerators

- **nvidia** - NVIDIA GPUs (fully implemented)
- **gaudi** - Intel Gaudi (placeholder for future)

## License

GPL-2.0-or-later
