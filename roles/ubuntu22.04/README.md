```markdown
# Ansible CIS Benchmark Role

This Ansible role implements security configurations based on the CIS (Center for Internet Security) Benchmark for Ubuntu servers. It is compatible with Ansible versions 2.12.0 and above.

## Configuration

You can configure variables in `defaults/main.yml`.

### On-Premises Ubuntu Servers

If you're using an on-premises Ubuntu server, set the following variable in `defaults/main.yml`:

```yaml
ubtu22cis_rule_1_4_3: true
```

### Cloud Servers

For cloud servers, the default setting is `false`.

### EC2 Pipeline

The role includes settings for running in an EC2 pipeline:

```yaml
system_is_ec2: true
```

This variable is used to skip events in the EC2 instance testing pipeline.

## Usage

### Running Specific CIS Security Levels

To apply a specific CIS security level, navigate to the `foldername/` directory and execute the playbook with the desired tag. For example, to apply level 1 security configurations:

```bash
ansible-playbook playbook.yml --tags=ubuntu22.04-level1
```

### Applying Both CIS Levels

To apply both level 1 and level 2 CIS security configurations, navigate to `foldername/roles/ubuntu22.04/` directory and run the main playbook:

```bash
cd foldername/roles/ubuntu22.04
ansible-playbook main.yml
```

## Note

Review the playbook and configuration files before execution to ensure compatibility and desired outcomes.

## Contributions

Contributions are welcomed! Please submit any improvements or suggestions via pull requests.

## License

This project is licensed under the [MIT License](LICENSE).
