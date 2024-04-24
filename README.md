# WSL2 Compacter 🗜

## A small script for Windows 10 Home users to compact their WSL2 disks

Inspired by [this post on GitHub about WSL2 filling hard disks](https://github.com/microsoft/WSL/issues/4699#issuecomment-627133168).
Original code by [mikemaccana / compact-wsl2-disk](https://github.com/mikemaccana/compact-wsl2-disk).

This script will:

 - Check for an elevated shell.
 - Find your `vhdx` file(s) in the default paths of
     * WSL2 distros (`C:\Users\<NAME>\AppData\Local\Packages\CanonicalGroupLimited...`)
     * Docker WSL2 distros (`C:\Users\<NAME>\AppData\Local\Docker`)
 - Shut down WSL2
 - Compact all found disks with [`diskpart`](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart)

After that just open another Linux terminal and WSL2 will restart automatically.

## Warning

1. I am a stranger on the internet asking you to run a powershell script. You should probably look inside the script [`compact-wsl2-disk.ps1`](compact-wsl2-disk.ps1) and make sure you understand what it does.

2. This will stop WSL. So save your work in Linux.

## Usage

Open Powershell as Administrator and run:

`powershell.exe .\compact-wsl2-disk.ps1`

## PRs are welcome!

Please file pull requests instead of just asking for things. Thanks!

## Fixes over the original code
The following fixes were made to the original code:
- Script elevation.
- Use `Push-Location` and `Pop-Location` to get back to the same location you started at.
- Support for account names with spaces like `Kees Bakker`.
- Script lines are made yellow.
- PowerShell linted.
## License

MIT

## Thanks

[This person on StackOverflow](https://stackoverflow.com/questions/64772243/can-diskpart-take-command-line-parameters-or-can-i-fake-them-with-powershell) and [everyone on the WSL GitHub](https://github.com/microsoft/WSL/issues/4699) and [R0Wi](https://github.com/R0Wi).
