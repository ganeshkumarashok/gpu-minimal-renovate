# gpu-minimal-renovate
Minimal repro for updating URLs from a source

This is to auto-update GRID GPU driver versions for Ubuntu 22.x, based on this custom source: https://raw.githubusercontent.com/Azure/azhpc-extensions/master/NvidiaGPU/resources.json.

## Current behavior
It auto-updates to the latest GRID driver version, for the appropriate distro (Ubuntu 22.04) but it does not auto-update the URL source for the build. 

This has the output of the raw JSON from the custom source, and the equivalent JSONata query, which is slightly different from the custom transformTemplate query: https://try.jsonata.org/5eXbFg9Bg. 

The output above contains `version` and `url` (based on the `DirLink`). 

I see this debug log in the renovate logs, with the newVersion but I don't see the new URL. 

```DEBUG: packageFiles with updates
{
  "baseBranch": "main"
  "config": {
    "regex": [
      {
        "deps": [
          {
            "depName": "nvidia-grid-driver",
            "currentValue": "512.161.08",
            "datasource": "custom.nvidia-grid-driver",
            "versioning": "loose",
            "replaceString": "# renovate: datasource=custom.nvidia-grid-driver depName=nvidia-grid-driver versioning=loose\n  version: \"512.161.08\"\n  url: \"https://download.microsoft.com/download/8/d/a/8da4fb8e-3a9b-4e6a-bc9a-72ff64d7a13c/NVIDIA-Linux-x86_64-512.161.08-grid-azure.run\"",
            "updates": [
              {
                "bucket": "major",
                "newVersion": "535.161",
                "newValue": "535.161",
                "newMajor": 535,
                "newMinor": 161,
                "newPatch": null,
                "updateType": "major",
                "branchName": "renovate/nvidia-grid-driver-535.x"
              }
            ],
            "packageName": "nvidia-grid-driver",
            "warnings": [],
            "currentVersion": "512.161.08",
            "isSingleVersion": true,
            "fixedVersion": "512.161.08"
          }
        ],
        "matchStrings": [
          "#\\s*renovate:\\s*(datasource=(?<datasource>.*?)\\s*)?depName=(?<depName>.*?)(\\s*versioning=(?<versioning>.*?))?\\s*.*?version.*\\\"(?<currentValue>.*?)\\\"\\s*(url:\\s*\\\"(?<currentUrl>.*?)\\\")?"
        ],
        "packageFile": "driver_config.yml"
      }
    ]
  }
}
```


## Expected behavior

I expect it to auto-update in driver_config.yml, both the driver version and the source URL for the run file ("DirLink": "https://download.microsoft.com/download/8/d/a/8da4fb8e-3a9b-4e6a-bc9a-72ff64d7a13c/NVIDIA-Linux-x86_64-535.161.08-grid-azure.run"). 

## Link to the Renovate issue or Discussion

Put your link to the Renovate issue or Discussion here.
