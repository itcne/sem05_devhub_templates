# Using This Template

This file provides guidance on how to use this Ansible Execution Environment template.

## Prerequisites

- Docker or Podman installed
- Ansible Builder (`pip install ansible-builder`)
- Ansible Navigator (`pip install ansible-navigator`)

## Customization

### Python Dependencies

Edit the `requirements.txt` file to add any Python modules needed by your automation:

```
# Add your Python dependencies here
boto3>=1.28.0
netaddr>=0.8.0
```

### Ansible Collections

Edit the `requirements.yml` file to add any Ansible collections needed:

```yaml
collections:
  - name: amazon.aws
    version: ">=5.0.0"
  - name: community.general
    version: ">=7.0.0"
```

### System Packages

Edit the `bindep.txt` file to add any system packages needed:

```
# Add your system dependencies here
rsync [platform:rpm]
openssh [platform:rpm]
```

## Building the Execution Environment

```bash
# Build the image
ansible-builder build -t {{ values.name }}:latest .

# Test the image
ansible-navigator exec --execution-environment-image {{ values.name }}:latest -- ansible --version
```
