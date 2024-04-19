# fancy_zhs_prompt

This repository contains my customized zsh configuration, inspired by the Kali Linux terminal setup.

## Features

- **Customized Prompt**: The prompt is designed to be visually appealing and functional.
- **Python-centric**: As I primarily code in Python, this configuration includes a helpful `cd()` function.
  - The `cd()` function automates the activation and deactivation of virtual environments.
  - When navigating into a directory containing a virtual environment (`./.env`), it automatically activates the environment.
  - If already in a virtual environment and navigating out of it, the function deactivates the environment.

## Usage

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/your-username/fancy_zhs-prompt.git
   ```

2. Copy the `.zshrc` file to your home directory:

   ```bash
   cp fancy_zhs-prompt/.zshrc ~/.zshrc
   ```

3. Source the `.zshrc` file to apply the changes:

   ```bash
   source ~/.zshrc
   ```

## Contribution

Feel free to contribute to this repository by suggesting improvements or additional features. Fork the repository, make your changes, and submit a pull request. Your contributions are highly appreciated!

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.
