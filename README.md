# vLLM Playground Collection

Ansible collection for configuring RHEL 10 servers to run vLLM playground with GPU support.

## Roles

| Role | Description |
|------|-------------|
| `rhel_workload_accelerator_config` | Configures NVIDIA GPU drivers and container toolkit |
| `rhel_workload_vllm_playground` | Installs vLLM playground and pulls container images |

## Requirements

- RHEL 10 target host
- Valid Red Hat subscription (for CRB repository)
- NVIDIA GPU (for GPU mode)

## Quick Start

```yaml
---
- name: Configure RHEL 10 for vLLM Playground
  hosts: vllm_servers
  vars:
    ACTION: provision
  roles:
    - rhel_workload_accelerator_config
    - rhel_workload_vllm_playground
```

Run with:
```bash
ansible-playbook -i inventory site.yml
```

## CPU-Only Mode

Skip the accelerator role and set CPU mode:

```yaml
---
- name: Configure RHEL 10 for vLLM Playground (CPU-only)
  hosts: cpu_servers
  vars:
    ACTION: provision
    rhel_workload_vllm_playground_accelerator_type: "none"
    rhel_workload_vllm_playground_pull_images_mode: "cpu"
  roles:
    - rhel_workload_vllm_playground
```

## Cleanup

Set `ACTION: destroy` to remove the configuration.

## License

GPL-2.0-or-later
