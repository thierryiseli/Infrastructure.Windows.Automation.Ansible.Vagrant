# Infrastructure.Windows.Automation.Ansible.Vagrant

Run Ansible for windows host with vagrant (WITHOUT WSL).

## Getting Started

### Prerequisites

| Program | Version | Link | Info |
|-------------|-------------|-----|--|
| Windows | 10 | https://www.microsoft.com/de-de/software-download/windows10 | You need to have a local administrator account on your windows host |
| Vagrant | >= 2.2.9 | https://www.vagrantup.com/downloads.html | N/A |
| VirtualBox | >= 6.1 | https://www.virtualbox.org/ | N/A |

See paragraph *Installing* if prerequisites are missing. 

### Preparing

Clone or download the current repository to your preferred location.

### Installing

> Only if the prerequisites are missing.

If you have not installed chocolatey on your windows host, please refer to https://chocolatey.org/install.

Open Command Prompt as administrator and switch to the location of the cloned or copied repository:

```
cd yourLocalRepositoryPath
```

Run command line script `installing.cmd` on your Windows host (as administrator):

```
installing.cmd
```

## Running

Open Command Prompt as administrator and switch to the location of the cloned or copied repository:

```
cd yourLocalRepositoryPath
```

Execute the following command on your Command Prompt:

```
vagrant up
```

Enter virtual machine name for your ansible master vm.
Afterwards the questions for administrator username and password appears.
After that wait until the VM is created and ansible is executed.

### Rerun ansible

Use the most commonly used command to run vagrant again: 

```
vagrant provision
```

## Authors

- [Thierry Iseli](https://github.com/thierryiseli) - *Initial work*

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Built With

- [Vagrant](https://www.vagrantup.com/)
- [Ansible](https://www.ansible.com/)
