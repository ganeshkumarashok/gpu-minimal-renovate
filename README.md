# gpu-minimal-renovate
Minimal repro for updating URLs from a source

This is to auto-update GRID GPU driver versions for Ubuntu 22.x, based on this source URL: https://raw.githubusercontent.com/Azure/azhpc-extensions/master/NvidiaGPU/resources.json.

## Current behavior
It auto-updates to the latest GRID driver version, for the appropriate distro (Ubuntu 22.04) but it does not auto-update the URL source for the build. 

## Expected behavior

I expect it to auto-update both the driver version and the source URL ("DirLink": "https://download.microsoft.com/download/8/d/a/8da4fb8e-3a9b-4e6a-bc9a-72ff64d7a13c/NVIDIA-Linux-x86_64-535.161.08-grid-azure.run"). 

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.
