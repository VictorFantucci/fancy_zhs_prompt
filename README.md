# FANCY ZHSRC PROMPT

This repository contains my customized zshrc configuration, inspired by the Kali Linux terminal setup.

## Features

- **Customized Prompt**: The prompt is designed to be visually appealing and functional.
- **Python-centric**: As I primarily code in Python, this configuration includes a helpful `cd()` function.
  - The `cd()` function automates the activation and deactivation of virtual environments.
  - When navigating into a directory containing a virtual environment (`./env`), it automatically activates the environment.
  - If already in a virtual environment and navigating out of it, the function deactivates the environment.
    - For Python developers like me, navigating through project directories can be a frequent task. That's why I've added a handy feature to the `cd()` function:

    ```bash
    function cd() {
      builtin cd "$@"
    
      if [[ -z "$VIRTUAL_ENV" ]] ; then
        ## If env folder is found then activate the virtualenv
        if [[ -d ./env ]] ; then
          source ./env/bin/activate
        fi
      else
        ## check if the current folder belongs to an earlier VIRTUAL_ENV folder
        # if yes, do nothing
        # else, deactivate
        parentdir="$(dirname "$VIRTUAL_ENV")"
        if [[ "$PWD"/ != "$parentdir"/* ]] ; then
          deactivate
        fi
      fi
    }
    ```
  
  With this function, whenever you change directories, it automatically activates a virtual environment if it finds one in the `env` folder. This saves you the hassle of manually activating it every time you switch projects.

## Usage

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/VictorFantucci/fancy_zhs-prompt.git
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

## Additional Resources

- [How to Make Ubuntu Terminal Look like Kali Linux](https://linuxopsys.com/topics/make-ubuntu-terminal-look-like-kali-linux)
- [How to automatically activate virtualenvs when cd'ing into a directory](https://stackoverflow.com/questions/45216663/how-to-automatically-activate-virtualenvs-when-cding-into-a-directory)

