# Reproducible Windows 11 Setup

This repository provides configuration files to make your Windows 11 setup as reproducible as NixOS. With these files, you can automate both the Windows installation process and the installation of your preferred applications.

## Overview

- **`winget_packages.json`**  
  A JSON file that lists the packages to be installed via [Winget](https://github.com/microsoft/winget-cli). This allows you to easily recreate your development environment by importing the package list.

- **`autounattend.xml`**  
  An unattended installation configuration for Windows 11. This file helps automate the Windows installation process with your customized settings.

## How to Use

### Unattended Windows 11 Installation

1. **Create a Bootable USB**:
   - Download the Windows 11 ISO from [Microsoft](https://www.microsoft.com/software-download/windows11).
   - Use a tool like [Rufus](https://rufus.ie/) to create a bootable USB drive with the Windows 11 ISO.
2. **Prepare for Unattended Setup**:

   - Place the `autounattend.xml` file in the root directory of your bootable USB drive.
   - Boot your computer from the USB drive. The Windows Setup will automatically use the `autounattend.xml` file to configure and install Windows 11 according to your predefined settings.

3. **Customize Your autounattend.xml**:  
   If you wish to generate and customize your own `autounattend.xml` file, you can use the [Unattend Generator](https://schneegans.de/windows/unattend-generator/). This tool provides an easy interface for creating a personalized unattended installation file.

### Post-Installation Package Setup

1. **Open PowerShell or Terminal**:  
   After Windows 11 installation is complete, open PowerShell or your preferred terminal.

2. **Import Winget Package List**:  
   Run the following command to install all packages listed in `winget_packages.json`:
   ```powershell
   winget import winget_packages.json
   ```

````

Winget will then automatically install each of the packages specified in the JSON file.

## Customization

- **Modify Package List**:
  Feel free to update the `winget_packages.json` file with additional or alternative packages to suit your needs.
- **Adjust Windows Installation Settings**:
  Customize the `autounattend.xml` file to adjust settings such as locale, time zone, disk partitions, user accounts, and more.

## Repository Structure

```
.
├── winget_packages.json  # List of Winget packages to install
├── autounattend.xml      # Unattended installation configuration for Windows 11
└── README.md             # This file
```

## License

This repository is licensed under the [MIT License](LICENSE).
````
