# Flowchart Collection

These Mermaid flowcharts can be viewed on GitHub. Each describes the main control flow of an operation.

## Add Student
```mermaid
flowchart TD
    A([Start]) --> B[/Enter roll number/]
    B --> C{Roll number exists?}
    C -- Yes --> D[Show duplicate message]
    D --> Z([End])
    C -- No --> E[/Enter profile details/]
    E --> F[/Enter subjects, marks, attendance, clubs/]
    F --> G{Inputs valid?}
    G -- No --> F
    G -- Yes --> H[Store profile dictionary]
    H --> I[Update department, subject, club sets]
    I --> J[Show success]
    J --> Z
```

## Search Student
```mermaid
flowchart TD
    A([Start]) --> B[/Enter roll number/]
    B --> C{Record exists?}
    C -- Yes --> D[Display student profile]
    C -- No --> E[Display not found]
    D --> Z([End])
    E --> Z
```

## Update Record
```mermaid
flowchart TD
    A([Start]) --> B[/Enter roll number/]
    B --> C{Record exists?}
    C -- No --> D[Display not found]
    D --> Z([End])
    C -- Yes --> E[/Enter changed values/]
    E --> F[Update selected fields]
    F --> G[Show success]
    G --> Z
```

## Delete Record
```mermaid
flowchart TD
    A([Start]) --> B[/Enter roll number/]
    B --> C{Record exists?}
    C -- Yes --> D[Delete profile]
    D --> E[Show success]
    C -- No --> F[Show not found]
    E --> Z([End])
    F --> Z
```

## Display Records
```mermaid
flowchart TD
    A([Start]) --> B{Any records?}
    B -- No --> C[Show no records]
    B -- Yes --> D[Loop through profiles]
    D --> E[Display each profile]
    E --> F{More profiles?}
    F -- Yes --> D
    F -- No --> Z([End])
    C --> Z
```

## Calculate Average
```mermaid
flowchart TD
    A([Start]) --> B[Collect all marks]
    B --> C{Any marks?}
    C -- No --> D[Show no marks]
    C -- Yes --> E[Sum marks / count marks]
    E --> F[Display average]
    D --> Z([End])
    F --> Z
```

## Generate Report
```mermaid
flowchart TD
    A([Start]) --> B[Count students]
    B --> C[Display unique collections]
    C --> D{Records and marks available?}
    D -- Yes --> E[Calculate average and highest scorer]
    D -- No --> F[Skip mark summary]
    E --> G[Group students by department]
    F --> G
    G --> H[Display report]
    H --> Z([End])
```
