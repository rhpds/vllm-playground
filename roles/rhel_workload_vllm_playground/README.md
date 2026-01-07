# rhel_workload_vllm_playground

Installs vLLM playground on RHEL 10 servers.

## What It Does

- Installs `vllm-playground` via pip
- Optionally installs benchmark tools (guidellm)
- Pre-pulls vLLM container images

## Requirements

- RHEL 10
- Python 3 with pip
- Podman (for container image pulls)
- GPU drivers installed (if using GPU mode) - use `rhel_workload_accelerator_config` role

## Usage

```yaml
- hosts: vllm_servers
  vars:
    ACTION: provision
  roles:
    - rhel_workload_vllm_playground
```

After installation, run:
```bash
vllm-playground
```

## Variables

See [defaults/main.yml](defaults/main.yml) for all configurable variables.

## License

GPL-2.0-or-later
