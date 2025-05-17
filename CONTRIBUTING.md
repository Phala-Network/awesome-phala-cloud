# Contributing Guidelines

Thank you for your interest in contributing to Awesome Phala Cloud! This guide outlines the requirements for submitting new templates.

## Submitting a New Template

To submit a new template, please follow these steps:

1. Modify `templates/config.json` and add your template entry following the schema format
2. Ensure your repository directory contains the following files:
   - `README.md`: Detailed documentation and usage instructions
   - `docker-compose.yml`: Deployment configuration
3. Update the project's `README.md` to include your template in the list of available templates
4. (Optional) Add an icon in the `templates/icons` directory:
5. (Optional) Add a "Deploy to Phala Cloud" button to your template's `README.md`:
   ```markdown
   [![](https://cloud.phala.network/deploy-button.svg)](https://cloud.phala.network/templates/{template_id})
   ```
   Replace `{template_id}` with your actual template ID

Thank you for your contribution!
