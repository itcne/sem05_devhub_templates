# ${{ values.name }} - Ansible Execution Environment

${{ values.description }}

## 📁 Files

| File | Purpose |
|------|---------|
| `execution-environment.yml` | Main ansible-builder configuration (UBI9 Python 3.12) |
| `requirements.txt` | Python dependencies (pip packages) |
| `requirements.yml` | Ansible Galaxy collections |
| `bindep.txt` | System packages (RPM/DEB) |

## 🚀 Quick Start

```bash
# Install tools
pip install ansible-builder ansible-navigator

# Build the execution environment
ansible-builder build -t ${{ values.name }}:latest .

# Test it works
ansible-navigator exec --execution-environment-image ${{ values.name }}:latest -- ansible --version
```

## 🧪 Testing

```bash
# Basic test - check collections
ansible-navigator exec --execution-environment-image ${{ values.name }}:latest -- ansible-galaxy collection list

# Run a test playbook
ansible-navigator run test-playbook.yml --execution-environment-image ${{ values.name }}:latest
```

## 🔄 CI/CD

${{ values.enableAutomatedBuilds === true && 
"This repository is configured with automated CI/CD workflows that will:\n\n" +
"1. Build the execution environment image\n" +
"2. Run tests to validate the image\n" +
"3. Publish the image to " + values.registry + "\n" +
"4. Create a release with proper version tagging\n\n" +
"The image will be available at: `" + values.registry + "/" + values.name + ":latest`" ||
"This repository can be configured with CI/CD workflows. See the `.github/workflows` directory for examples." }}
