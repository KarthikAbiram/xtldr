## Help
`dotnet new webapi --help`

## Create Project
To use controllers style project, use below command:
`dotnet new webapi --use-controllers`

To specify a subfolder for creating the project, use:
`dotnet new webapi -o <subfolder name>`

## Run
To run, use the below commnad, which would start the service and open the swagger UI in the default browser:
`dotnet watch run`

Alternatively, you can use `dotnet run` to start the service. But you need to know the exact swagger UI URL to open in browser. Just opening the root domain, will not show up swagger and would result in 404 - webpage not found error.

## VS Code Commands
| Command                        | Description                                                          |
| ------------------------------ | -------------------------------------------------------------------- |
| prop + Tab | Creates a placeholder integer property within the class |
| ctor + Tab | Creates a placeholder constructor within the class |

## Courses
1. [ASP.NET Web API .NET 8 Tutorial 2024](https://www.youtube.com/playlist?list=PL82C6-O4XrHfrGOCPmKmwTO7M0avXyQKc)