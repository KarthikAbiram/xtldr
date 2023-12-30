---
hide:
  - navigation
---
# OPA
OPA stands for Open Policy Agent. It is an open source framework which services can use to check whether a user is allowed to access a resource based on custom rules that you can define.

## Getting Started with OPA
[Getting Started with OPA by Styra](https://academy.styra.com/courses/opa-by-example)

## Rego Language
[OPA Policy Language](https://www.openpolicyagent.org/docs/latest/policy-language/)

## Sample OPA
Create below files in a base directory.

### policy.rego
```
package test

import future.keywords.if

default allow := true
default deny := false

default hello := {"hello","world"}

full_input := input
full_path := input.path
split_paths := split(input.path,"//")
```
### test_input.json
This is a test input file to use for testing using "opa eval".
```
{
  "path": "my/path/goes/here/file"
}
```
### Download OPA
1. Download [OPA EXE for Windows](https://openpolicyagent.org/downloads/latest/opa_windows_amd64.exe)
2. Rename "opa_windows_amd64.exe" to "opa.exe".
3. Place the "opa.exe" in the base folder.

### OPA Eval Command for Testing
Run below command from command prompt from the base folder which contains the opa.exe, policy.rego and test_input.json.
```
opa.exe eval --data policy.rego --input test_input.json --format raw "data.test"
```
This would evaluate and return the output of all the variables/rules in the policy.rego file.