# GoConcurrency

* Making progress on more than one task simultaneously is known as **concurrency**. 
Go has rich support for concurrency using **goroutines** and **channels**.

* A **goroutine** is a function that is capable of running concurrently with other functions.

```go
package main

import (
  "fmt"
)

func f(n int) {
  for i := 0; i < 10; i++ {
    fmt.Println(n, ":", i)
  }
}

func main() {
  go f(0)
  var input string
  fmt.Scanln(&input)
}
```

* This program consists of **two goroutines**. The first goroutine is implicit and is the **main function** itself.
The second goroutine is created when we call **go f(0)**.
