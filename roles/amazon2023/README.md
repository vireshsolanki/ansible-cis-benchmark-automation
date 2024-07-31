```markdown
# Ansible CIS Benchmark Role

This Ansible role implements security configurations based on the CIS (Center for Internet Security) Benchmark for Amazon2023 servers. It is compatible with Ansible versions 2.10.0 and above.

## Configuration

You can configure variables in `defaults/main.yml`.

#### Technical Dependencies

Python3
Ansible 2.10+
python3-libselinux (installed in prereqs if required)
collections found in collections/requirements.yml
Use this version to run

ansible-base 2.10.17 - python 3.8
#### Requirements
Amazon 2023

Access to download or add the goss binary and content to the system if using auditing (other options are available on how to get the content to the system.)
CentOS stream - while this will generally work it is not supported and requires the following variable setting

```bash
os_check: false
```
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
ansible-playbook playbook.yml --tags=amazon2023-level1-server
```

### Applying Both CIS Levels

To apply both level 1 and level 2 CIS security configurations, navigate to `foldername/roles/amazon2023/` directory and run the main playbook:

```bash
cd foldername/roles/amazon2023
ansible-playbook main.yml
```

## Note

Review the playbook and configuration files before execution to ensure compatibility and desired outcomes.

## Contributions

Contributions are welcomed! Please submit any improvements or suggestions via pull requests.

## License

This project is licensed under the [MIT License](LICENSE).
