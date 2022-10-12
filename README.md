# GoSecure
Simple Golang Security

# Code
```go
package main

import (
	"fmt"
	"github.com/shirou/gopsutil/process"
)

func main() {
	for {
		pids, _ := process.Pids()

		for _, p := range pids {
			pid, _ := process.NewProcess(p)
			name, _ := pid.Name()

			switch name {
			case "x64dbg.exe":
				fmt.Println("Killed:", name)
				pid.Kill()
			case "x32dbg.exe":
				fmt.Println("Killed:", name)
				pid.Kill()
			}
		}
	}

}
```

# Install Package
```cmd
go get github.com/shirou/gopsutil/process
```
