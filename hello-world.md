# Hello World

เปิด terminal สร้าง directory ใหม่แล้วเข้าไปสั่ง init module ใหม่ตามนี้

```
$ mkdir hello-world
$ cd hello-world
$ go mod init hello-world
```

สร้างไฟล์ main.go แล้วเขียนโค้ด main package กับ main function ตามนี้

```go
package main

import (
    "fmt"
)

func main() {
    fmt.Println("Hello World")
}
```

สั่งรัน

```
$ go run main.go
Hello World
```
