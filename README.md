# hyprwsname

A simple bash script to rename the current Hyprland workspace.

## Description

`wsname.sh` is a utility that allows you to quickly rename your active Hyprland workspace from the command line. It automatically detects the current workspace and applies the new name using Hyprland's IPC interface.

## Installation

1. Clone this repository or download the script
2. Make the script executable:
   ```bash
   chmod +x wsname.sh
   ```

3. (Optional) Make it globally available:
   ```bash
   ln -sf /path/to/wsname.sh ~/.local/bin/wsname
   ```
   Ensure `~/.local/bin` is in your PATH.

## Usage

From the script directory:
```bash
./wsname.sh "Workspace Name"
```

If installed globally:
```bash
wsname "Workspace Name"
```

## Examples

```bash
# Rename current workspace to "Development"
./wsname.sh "Development"

# Rename to "Web Project"
./wsname.sh "Web Project"

# Single word names work too
./wsname.sh Gaming
```

## Requirements

- Hyprland window manager
- `hyprctl` command (comes with Hyprland)
- Bash

## How it Works

1. Retrieves the current active workspace ID using `hyprctl activeworkspace`
2. Uses `hyprctl dispatch renameworkspace` to set the new name
3. Provides feedback on success or failure