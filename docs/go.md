---
hide:
  - navigation
---

# Go

## Install
1. Install [Go](https://go.dev/dl/).
2. Install [Go Extension for VS Code](https://marketplace.visualstudio.com/items?itemName=golang.go).

## Quick Start
1. A sample application, which will add two numbers passed from cmdline arguments and returns the result.
2. Create add.go with below code:
```
package main

import (
	"fmt"
	"os"
	"strconv"
)

func main() {
	if len(os.Args) != 3 {
		fmt.Println("Usage: add <int1> <int2>")
		return
	}

	// Convert arguments to integers
	a, err1 := strconv.Atoi(os.Args[1])
	b, err2 := strconv.Atoi(os.Args[2])

	if err1 != nil || err2 != nil {
		fmt.Println("Both arguments must be valid integers.")
		return
	}

	// Add and print the result
	sum := a + b
	fmt.Printf("%d\n", sum)
}
```

## Run
In terminal, use below command:
```
go run add.go 1 2
```

## Build
To build the application to an executable:
```
go build -o add.exe add.go
```