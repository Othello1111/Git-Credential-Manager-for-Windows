#Git Credential Manager for Windows
The [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows) provides secure Git credential storage for Windows. It's the successor to the [Windows Credential Store for Git  (git-credential-winstore)](https://gitcredentialstore.codeplex.com/), which is no longer maintained.

This project includes:

 * Secure password storage in the Windows Credential Store
 * Multi-factor authentication support for Visual Studio Online.
 * Two-factor authentication support for GitHub
 * Personal Access Token generation and usage support for Visual Studio Online and GitHub
 * Non-interative mode support for Visual Studio Online backed by Azure Directory
 * Optional settings for build agent optimization

This is a community project so feel free to contribute ideas, submit bugs, fix bugs, or code new features.

## Download and Install
To use the Git Credential Manager for Windows, you can download the [latest installer](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases). To install, extract the .zip file and run install.cmd from an administrator command prompt.

## Build agents
Build agents cannot manage modal dialogs, therefore we recommended the following configuration.
```
git config --global credential.interactive never
```

Build agents often need to minimize the amount of network traffic they generate. 

To avoid Microsoft Account vs. Azure Active Directory look-up against a Visual Studio Online account use: 
```
git config --global credential.authority Azure
```

To avoid unnecessary service account credential validation use: 
```
git config --global credential.validate false
```

## Contribute
There are many ways to contribue.
* [Submit bugs](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/issues) and help us verify fixes as they are checked in.
* Review [code changes](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/pulls).
* Contribute bug fixes and features.

For code contributions, you will need to complete a Contributor License Agreement (CLA). Briefly, this agreement testifies that you grant us permission to use the submitted change according to the terms of the project's license, and that the work being submitted is under the appropriate copyright.

Please submit a Contributor License Agreement (CLA) before submitting a pull request. You may visit https://cla.microsoft.com to sign digitally. Alternatively, download the agreement [Microsoft Contribution License Agreement.pdf](https://cla.microsoft.com/cladoc/microsoft-contribution-license-agreement.pdf), sign, scan, and email it back to <cla@microsoft.com>. Be sure to include your github user name along with the agreement. Once we have received the signed CLA, we'll review the request.

## Debugging
To enable logging, use the following:
```
git config --global credential.writelog true
```

Log files will be written to the repo's local `.git/` folder.

## License
This project uses the [MIT License](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/blob/master/LICENSE.txt).
