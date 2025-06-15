# Ansible Execution Environment Template

This template provides a starter structure for creating Ansible Execution Environments - containerized environments for running Ansible playbooks and roles with all required dependencies pre-installed.

## Description

An Ansible Execution Environment is a container image that serves as an isolated environment for running Ansible automation. It packages:

- Ansible core or Ansible community packages
- Python dependencies required by Ansible collections
- System-level dependencies required by Python packages or modules
- Ansible collections

This template helps you to quickly bootstrap a new Ansible Execution Environment configuration with the best practices for structure and content.

## Usage

1. Use this template through the Developer Hub to create a new Ansible Execution Environment project
2. Select your preferred container registry (GitHub Container Registry, Docker Hub, or Quay.io)
3. Customize the generated files to match your specific requirements
4. Build your execution environment using the included configuration
5. Publish the execution environment to your container registry
6. Use it in your Ansible automation workflows

## Structure

- `execution-environment.yml` - Main configuration file for the execution environment
- `requirements.txt` - Python dependencies
- `requirements.yml` - Ansible collections
- `bindep.txt` - System-level dependencies
- `.github/workflows/ci.yml` - GitHub Actions workflow for automated building and publishing (configured for selected container registry)

## Source and Credits

This template is based on the [Ansible Execution Environment Blueprint](https://github.com/itcne/ansible-ee-blueprint) maintained by ITCNE. The blueprint provides a robust foundation for creating standardized Ansible Execution Environments following best practices.

## Additional Resources

- [Ansible Execution Environment Documentation](https://ansible.readthedocs.io/projects/builder/en/latest/)
- [Ansible Builder Documentation](https://ansible.readthedocs.io/projects/builder/en/latest/)
- [Ansible-Runner Documentation](https://ansible-runner.readthedocs.io/en/latest/execution_environments.html)

## License

This template is licensed under [LICENSE](../LICENSE).

