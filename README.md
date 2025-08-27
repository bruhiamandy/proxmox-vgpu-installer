This is a little Bash script that configures a Proxmox 8 or 9 server to use Nvidia vGPU's. 

For further instructions see my blogpost at https://wvthoog.nl/proxmox-7-vgpu-v3/

Changes in version 1.2
- Added support for Proxmox 9.
- Removed support for Proxmox 7.
- Removed kernel pinning as it's no longer necessary.
- Integrated `pve-nvidia-vgpu-helper` for a more robust setup.
- Updated the host driver installation method.
- Updated supported vGPU driver versions to 18.3, 18.4, and 19.0.
- Removed support for older driver versions (16.x, 17.0).
- Switched from `megadl` to `wget` for downloading drivers.
- Updated vGPU host driver URLs.

Changes in version 1.1
- Added new driver versions
    16.2
    16.4
    17.0
- Added checks for multiple GPU's
- Added MD5 checksums on downloaded files
- Created database to check for PCI ID's to determine if a GPU is natively supported
- If multiple GPU's are detected, pass through the rest using UDEV rules
- Always write config.txt to script directory
- Use Docker for hosting FastAPI-DLS (licensing)
- Create Powershell (ps1) and Bash (sh) files to retrieve licenses from FastAPI-DLS

## To-Do
1.  Replace FastAPI-DLS with nvlts (https://git.collinwebdesigns.de/vgpu/nvlts).
2.  Add new GPU data to gpu_info.db (anyone can support?)