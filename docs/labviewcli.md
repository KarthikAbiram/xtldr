---
hide:
  - navigation
---
# LabVIEWCLI

## Install
Included as part of LabVIEW. Verify using below command in terminal:
`LabVIEWCLI`

If not installed, install from [NI Addons](https://www.ni.com/en/support/downloads/software-products/download.ni-labview-command-line-interface.html#558644)

## Prerequisites

## Examples
LabVIEWCLI Examples would be located at
C:\Users\Public\Documents\National Instruments\LabVIEW CLI\Examples

## Commands

### RunVI
VIs called by this operation must have the 4x2x2x4 connector pane pattern, like the one below:

```
C:\Users\Public\Documents\National Instruments\LabVIEW CLI\Examples\AddTwoNumbers\AddTwoNumbers.vi
```

Syntax: 
```
LabVIEWCLI -OperationName RunVI -VIPath <path of VI to run> <input arguments for VI>
```

Example: 
C:\Users\Public\Documents\National Instruments\LabVIEW CLI\Examples\RunVIExampleScript.bat

```
LabVIEWCLI -OperationName RunVI -VIPath "C:\Users\Public\Documents\National Instruments\LabVIEW CLI\Examples\AddTwoNumbers\AddTwoNumbers.vi" 123 456 
```
