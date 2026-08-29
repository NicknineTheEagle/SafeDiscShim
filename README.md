# SafeDiscShim
## Disclaimer
SafeDiscShim is purely designed as a compatibility tool: no security mechanisms are bypassed in the operation of this 
tool and SafeDisc protected games still require their original discs in order to function, even when using this tool.
Certain games may have additional compatibility issues outside of the SafeDisc protection; this tool makes no attempt to
fix such issues. Due to the techniques used, certain anti-malware programs may wrongly detect this software as being
malicious.

## Introduction
SafeDiscShim is a compatibility tool that allows for SafeDisc protected games which utilize the insecure Macrovision
Security Driver ("secdrv.sys") to run on modern versions of Windows which have said driver blacklisted. Previous methods
to restore functionality to these games relied on forcefully installing the driver, potentially opening security risks.

In contrast, this tool does not rely on any drivers to function. Instead, it automatically loads alongside SafeDisc
protected games and intercepts any communication requests that would have been sent to the driver, instead sending the 
expected response itself and allowing the game to boot.

## Installation Instructions
Download the [latest release](https://github.com/NicknineTheEagle/SafeDiscShim/releases/latest) and follow the instructions for SafeDisc version your game uses.

### SafeDisc 1
Rename drvmgt.asi from the release to drvmgt.dll and copy it next to the game executable.

### SafeDisc 2+
Simply copy both files from the release next to next to the game executable. You might need to rename dinput8.dll to one of the other system dll names supported by Ultimate ASI Loader, it depends on which libraries the game uses (see https://github.com/ThirteenAG/Ultimate-ASI-Loader).

## Logging
To aid with debugging, beta versions of SafeDiscShim will automatically create log files in the same folder as the 
executable. If you wish to disable this, set the environment variable "SAFEDISCSHIM_LOGLEVEL" with a value of "none".
