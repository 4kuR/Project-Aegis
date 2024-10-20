<img src="https://i.ibb.co/p41TdmT/mouse.png" alt="mouse" width="800" height="450" style="display: block; margin: auto;">

# Project Aegis

Project Aegis is a powerful Bash script designed to streamline the setup and execution of a PHP server and npm (Node Package Manager) processes. This script facilitates system package updates, project directory selection, and the management of server processes while logging relevant information. It is especially useful for developers working on PHP applications that require a local development server.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Script Functions Overview](#script-functions-overview)
- [Example Workflow](#example-workflow)
- [Cleanup](#cleanup)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)
- [Frequently Asked Questions (FAQs)](#frequently-asked-questions-faqs)

## Features

- **Automated System Update**: 
  - The script prompts the user for confirmation before updating the system packages. This feature ensures that your development environment is always up to date, which can help prevent compatibility issues with libraries and packages.
  - It runs `sudo apt update` and `sudo apt upgrade -y` in a new Konsole tab, allowing users to view the update progress while they continue with other tasks.

- **Dynamic Project Directory Selection**: 
  - The script intelligently searches for folders located directly inside the `public_html` directories within the user's home directory. This automated selection process saves time and minimizes errors by eliminating the need to manually specify paths.
  - Users can easily navigate and choose their project folder from a list, which enhances productivity and streamlines the development process.

- **Process Management**: 
  - Once the project directory is selected, the script initiates both the PHP server and npm processes, running them in separate Konsole tabs. 
  - This feature allows developers to monitor outputs in real-time, facilitating quicker debugging and adjustments. The script also handles process termination gracefully, ensuring no orphaned processes remain running.

- **Log Management**: 
  - The script automatically creates a log directory within the selected project folder to store important log files and environment variable backups.
  - This aids in monitoring and debugging, as users can easily access logs to review past states and actions taken during script execution.

- **User-Friendly Prompts**: 
  - At every step of the script, clear instructions and prompts guide the user through the process. This design choice ensures that even novice users can easily navigate and utilize the script without confusion.
  - Error handling is incorporated throughout, providing helpful messages that guide users on how to resolve issues or proceed with alternative steps.

- **Environment Backup**: 
  - The script backs up all current environment variables to a text file located in the log directory. This backup can be invaluable for troubleshooting and auditing purposes, as it provides a snapshot of the environment at the time the script was run.
  - Users can refer back to these backups to understand any changes made during the development process.

## Prerequisites

Before using the script, ensure you have the following installed on your system:

- **PHP**: 
  - Ensure PHP is installed and accessible via the command line. You can check if PHP is installed by running:
    ```bash
    php -v
    ```
  - If PHP is not installed, you can typically install it on Debian-based systems using:
    ```bash
    sudo apt install php
    ```

- **Node.js and npm**: 
  - Node Package Manager (npm) must also be installed. You can verify this by running:
    ```bash
    npm -v
    ```
  - If npm is not installed, you can install Node.js (which includes npm) by following the official [Node.js installation guide](https://nodejs.org/en/download/package-manager/).

- **Konsole**: 
  - The script uses `konsole` for terminal management; ensure it is installed on your system. You can usually install it via your package manager:
    ```bash
    sudo apt install konsole
    ```

- **Access Rights**: 
  - Ensure you have appropriate permissions to run commands with `sudo`, as the script requires administrative access to perform system updates and install necessary packages.

## Installation

To set up the Project Aegis script, follow these steps:

1. **Clone the Repository**: 
   - Open your terminal and run the following command to clone the repository to your local machine:
     ```bash
     git clone https://github.com/4kuR/ProjectAegis.git
     cd ProjectAegis
     ```

2. **Make the Script Executable**: 
   - Change the file permissions to make the script executable:
     ```bash
     chmod +x ProjectAegis.sh
     ```

3. **Install Dependencies**: 
   - Ensure all necessary dependencies are installed as outlined in the prerequisites section. If any dependencies are missing, the script will prompt you to install them.

4. **Configure Environment (if needed)**: 
   - If your projects require specific environment variables or configurations, ensure to set them up in your shell profile or within the script before running it.

## Usage

To run the script, execute the following command in your terminal:

```bash
./ProjectAegis.sh
```

## Script Functions Overview

The script consists of the following key functions:

- **update_system**: This function manages the system update process by executing necessary commands to update the package list and upgrade installed packages.

- **select_project_directory**: Facilitates the selection of a project directory by listing available directories in the `public_html` folder and allowing user navigation.

- **start_php_server**: This function starts the PHP development server in a new Konsole tab, allowing real-time monitoring of server output.

- **start_npm_process**: Launches npm processes as specified in the project’s `package.json` file in a separate Konsole tab for easy monitoring.

- **log_management**: Handles the creation and management of log files, ensuring that important information is captured for review and debugging.

- **backup_environment**: Backs up current environment variables to a text file in the log directory, allowing users to review the state of the environment at the time the script was executed.

## Example Workflow

1. Open your terminal and run the script using `./ProjectAegis.sh`.
2. Confirm the system updates when prompted by the script.
3. Select your project directory from the provided list.
4. Monitor the PHP and npm processes running in separate Konsole tabs.
5. Check the log directory for any relevant log files after the script execution.

## Cleanup

To clean up after using the script:

- Manually delete the log directory if it’s no longer needed.
- Ensure that all Konsole tabs are closed to terminate any orphaned processes.
- If there were any issues, review the log files for debugging information.

## Contributing

Contributions to Project Aegis are welcome! Please follow these steps to contribute:

1. Fork the repository on GitHub.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them with a clear message.
4. Push your changes to your forked repository.
5. Submit a pull request with a clear description of your changes.

## License

Project Aegis is licensed under the MIT License. See the LICENSE file for more details.

## Acknowledgements

Thanks to all contributors and users who provide feedback and help improve the Project Aegis script. Special thanks to the open-source community for the tools and libraries that make this project possible.

## Contact

For questions or support, please contact the maintainer at [aku.roininen@gmail.com].

## Frequently Asked Questions (FAQs)

**Q: How do I run the script?**  
A: Simply execute `./ProjectAegis.sh` in your terminal.

**Q: What if I encounter issues with dependencies?**  
A: Ensure you follow the prerequisites section and install any missing packages. If issues persist, consult the documentation or seek help from the community.

**Q: Can I customize the script?**  
A: Yes! Feel free to modify the script as per your requirements, especially the environment variables. Be sure to document any changes you make for future reference.

**Q: Is there a way to revert changes made by the script?**  
A: The script does not automatically revert changes, but you can review log files and backup information for manual restoration if necessary.

