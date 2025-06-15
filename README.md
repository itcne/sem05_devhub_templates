# Semester thesis 05 - Backstage Scaffolding Templates

This repository contains a collection of templates for the [Backstage Software Catalog](https://backstage.io/docs/features/software-templates/) that can be used to scaffold various types of projects. These templates are designed to help developers quickly create new projects with standardized configurations and best practices.

## Available Templates

| Template                                      | Description                                          | Documentation                             |
| --------------------------------------------- | ---------------------------------------------------- | ----------------------------------------- |
| [ansible-ee-template](./ansible-ee-template/) | Template for creating Ansible Execution Environments | [README](./ansible-ee-template/README.md) |

## How to Use

These templates can be registered in a Backstage instance by adding this repository to your Backstage software catalog. Follow these steps:

1. Add this repository URL to your Backstage software catalog
2. Navigate to the "Create" section in your Backstage instance
3. Select the desired template from the list
4. Follow the template's guided creation process

## Development

To add a new template to this collection:

1. Create a new directory with a descriptive name
2. Add the following files to your template directory:
   - `template.yaml`: Defines the template metadata and steps
   - `skeleton/`: Contains the files that will be scaffolded
   - `README.md`: Documents your template
   - `catalog-info.yaml`: Registers the template in the catalog

### Template Variable Syntax

When using template variables in your skeleton files, use the following syntax:

- Standard variable: `${{ values.variableName }}`
- With filters: `${{ values.variableName | function('arg') }}`
- For conditional sections, use the JavaScript ternary syntax: `${{ condition ? 'true text' : 'false text' }}`
- For files that need configuration but can't accept template variables (like GitHub Actions workflows), use string replacement in the template steps

## License

This project is licensed under the terms specified in [LICENSE](./LICENSE).
