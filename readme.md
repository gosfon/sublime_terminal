# Sublime Terminal
**This repository was Forked from [**the original author**](https://github.com/wbond/sublime_terminal)  
All updates in this repository are already adopted in there. Therefore, it is happy to use above.
**

Shortcuts and menu entries for opening a terminal at the current file, or the current root project folder in [Sublime Text](http://sublimetext.com/).

## Features

 - Opens a terminal in the folder containing the currently edited file
 - Opens a terminal in the project folder containing the currently edited file

## Installation

```bash
  # '$SublimeTextDir' is you Sublime Text install directory
  cd $SublimeTextDir/Data/Packages
  git clone https://github.com/gosfon/sublime_terminal Terminal
```

## Usage

 - **Open Terminal at File**
     Press *ctrl+shift+t* on Windows and Linux, or *cmd+shift+t* on OS X
 - **Open Terminal at Project Folder**
     Press *ctrl+alt+shift+t* on Windows and Linux, or *cmd+alt+shift+t* on OS X

In addition to the key bindings, terminals can also be opened via the editor context menu and the sidebar context menus.

## Package Settings

The default settings can be viewed by accessing the ***Preferences > Package Settings > Terminal > Settings – Default*** menu entry. To ensure settings are not lost when the package is upgraded, make sure all edits are saved to ***Settings – User***.

 - **terminal**
     - The terminal to execute, will default to the OS default if blank. OS X users may enter *iTerm.sh* to launch iTerm if installed.
     - *Default:* ***""***
 - **parameters**
     - The parameters to pass to the terminal. These parameters will be used if no [custom parameters](#custom-parameters) are passed via a key binding.
     - *Default:* ***[]***

### Examples

Here are some example setups:

#### Cmder on Windows

```js
{
  // Replace with your own path to cmder.exe
  "terminal": "C:\\Program Files\\cmder_mini\\cmder.exe",
  "parameters": ["/START", "%CWD%"]
}
```

#### xterm on GNU/Linux

```js
{
  "terminal": "xterm"
}
```

#### iTerm on OS X

```js
{
  "terminal": "iTerm.sh"
}
```

#### iTerm on OS X with tabs

```js
{
  "terminal": "iTerm.sh",
  "parameters": ["--open-in-tab"]
}
```

## Custom Parameters

With the parameters argument to the *open_terminal* and *open_terminal_project_folder* commands, it is possible to construct custom terminal environments.

The following is an example of passing the parameters *-T 'Custom Window Title'* to a terminal. Please note that this example is just an example, and is tailored to the XFCE terminal application. Your terminal may use the `-T` option for some other features or setting. Custom key bindings such as this would be added to the file opened when accessing the *Preferences > Key Bindings – User* menu entry (the file name varies by operating system).

```json
{
  "keys": ["ctrl+alt+t"],
  "command": "open_terminal",
  "args": {
    "parameters": ["-T", "Custom Window Title"]
  }
}
```

A parameter may also contain the *%CWD%* placeholder, which will be substituted with the current working directory the terminal was opened to.

```json
{
  "keys": ["ctrl+alt+t"],
  "command": "open_terminal",
  "args": {
    "parameters": ["-T", "Working in directory %CWD%"]
  }
}
```
