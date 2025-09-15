# vscode-user-installer

This is a small script that will install the latest version of VS Code for your user and continuously update it automatically without requiring sudo/root.

## Installation

### Method 1 - `curl`

Download the `code` executable script directly from GitHub into some folder in your PATH.

```sh
$ curl https://raw.githubusercontent.com/abrahammurciano/vscode-user-installer/refs/heads/main/code > ~/.local/bin/code
$ chmod +x ~/.local/bin/code
```

### Method 2 - `git`

Clone this repository wherever you like, then put the `code` executable script somewhere in your PATH.

```sh
$ git clone https://github.com/abrahammurciano/vscode-user-installer.git
$ cp ./vscode-user-installer/code ~/.local/bin
$ rm -rf ./vscode-user-installer
```

## Verify installation

Make sure it was installed correctly. The output of this command should be the location that you placed the `code` script, for example `$HOME/.local/bin/code`.
```sh
$ which code
```
If it isn't, add the folder where you put the `code` script (e.g. `~/.local/bin`) to your path and remove any aliases you previously set for code (if you want to keep your alias, make sure it launches the script and not any other `code` installed on the OS).

Then simply run `code`. This will install the latest version of code (if it's not already installed) and launch it.

For any GUI launchers to work with this installation instead of the system installation, remove them and create them again. (The shortcut in the application menu will already point to this installation.)

## Uninstall

If you want to uninstall this and switch back to the system version, remove the script from your PATH.
```sh
$ rm ~/.local/bin/code
```
And delete the `.desktop` file to revert the GUI launchers to the system version.
```sh
$ rm ~/.local/share/applications/code.desktop
```
