---
hide:
  - navigation
---

# PlantUML
## Online PlantUML Generator:
[Online PlantUML](https://www.plantuml.com/plantuml/)

## Sequence Diagram Syntax
[Sequence Diagram Syntax](https://plantuml.com/sequence-diagram)

### Steps to Install 
1. Install the [PlantUML VS Code Extension by Jebbs](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml)

=== "Option 1: Docker Installation"
    Run plantuml server using docker:
    ```
    docker run -d -p 8800:8080 plantuml/plantuml-server:jetty
    ```
    
    Configure plantuml server in VSCode Extension:  

    1. Click on the plantuml settings icon and then click on 'Extension Settings'.  
    ![PlantUML Settings Icon](\images\plantuml_extension_settings.png){ : style="height:250px"}
    2. Scroll down to 'Plantuml: Render' and 'Plantuml: Server' and configure them as below.
    ```
    Plantuml: Render: PlantUML Server
    Plantuml: Server: http://localhost:8800
    ```
    ![PlantUML Local Docker Server Configuration](\images\plantuml_local_docker_configuration.png){ : style="width:750px"}

=== "Option 2: Local Java Installation"
    If you wish, you can install PlantUML local server using Choco using below steps:
    For windows users,  [majkinetor](https://github.com/majkinetor "https://github.com/majkinetor")  introduced a way to install plantuml and its dependencies easily. Run  `cmd.exe`  as Administrator, and run two commands as follows (the first command is not needed and will fail if you already have chocolatey installed).

    ```
    @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"  
      
    choco install plantuml
    ```

    > If you've installed java, but still prompts "java not installed", please add java bin path to  `PATH`  environment variable.

### Usage
Create a file in VS Code with *.plantuml extension and create a uml diagram as per its syntax.

**Example:**  
```
@startuml
Bob -> Alice : hello
@enduml
```
Press **Alt + D** to preview the UML diagram. Kindly make sure that the docker container in running (if went with "Option 1: Docker Installation")