# Ignite

Multi-library start-up utility for Omnis project.

![](https://raw.githubusercontent.com/GiacomoManzoli/Ignite/master/res/wnd_info.png)

## Configuration and usage

At the startup, Ignite looks for a file `ignite.config.json` in the same folder of the library. If there isn't a configuration file, it asks a filepath and store the info in the `$userinfo` property of `Startup_Task`.

In the configuration file it's possible to define:

* `ProjectName`: the `$name` property of the Ignite menù;
* `BaseDir`: the relative path from the `Ignite.lbs` folder to the directory containg the libraries;  optional, the default value it's the same dir (`.`).
* `OpenAsPrivate`: boolean flag, if true the libraries are opened as private
* `Libs`: libraries to open. The libraries are open on the same order as the list.
	* `Name`: name of the `.lbs` file.
	* `FilePath`: optional, the relative (from `BaseDir`) or absolute filepath to the `.lbs` file. 
	* `DownloadUrl`: not yet implemented.
	* `Version`: for update - not yet implemented.

### Example

```json
{
    "ProjectName": "TestProject",
    "BaseDir": "./Test/",
    "OpenAsPrivate": false,
    "Libs": [
        {
            "Name": "Library1",
            "FilePath": "",
            "DownloadUrl": "https://github.com/GiacomoManzoli/IgniteTest/blob/master/Library1.lbs?raw=true",
            "Version": "1.0.0"
        },
        {
            "Name": "Library2",
            "FilePath": "./NestedFolder/",
            "DownloadUrl": "https://github.com/GiacomoManzoli/IgniteTest/blob/master/Library2.lbs?raw=true",
            "Version": "1.0.0"
        },
        {
            "Name": "Library3",
            "DownloadUrl": "https://github.com/GiacomoManzoli/IgniteTest/blob/master/Library3.lbs?raw=true",
            "Version": "1.0.0-alpha"
        },
        {
            "Name": "Library4",
            "FilePath": "/Users/gmanzoli/Dropbox/Kommander.lbs",
            "DownloadUrl": "https://github.com/GiacomoManzoli/IgniteTest/blob/master/Library3.lbs?raw=true",
            "Version": "1.0.0-alpha"
        }
    ]
}
```

## Future ideas

* Automatic update download
* Improved relative path support (e.g. `..`)
