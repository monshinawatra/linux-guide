# linux-guide

## WSL space reduction
ext4 located in `C:\Users\<your_username>\AppData\Local\Packages\<distro_package_name>\LocalState\ext4.vhdx`

[answer](https://superuser.com/questions/1606213/how-do-i-get-back-unused-disk-space-from-ubuntu-on-wsl2)

For Windows Pro or higher:
Use Optimize-VHD:
- Open PowerShell as administrator.
- Navigate to the directory containing the ext4.vhdx file.
- Run the command: `Optimize-VHD -Path .\ext4.vhdx -Mode full`

For Windows Home:
Use diskpart:
- Open a command prompt as administrator.
- Run the command: `diskpart`
- Inside diskpart, run the following commands: `select vdisk file="<path_to_ext4.vhdx>"`
- Run `compact vdisk`
