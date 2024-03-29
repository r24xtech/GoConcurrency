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

* Normally, when we invoke a function, our program will execute all the statement in a function and then return to the next line following the invocation. || With a **goroutine**, we return immediately to the next line and don't wait for the function to complete. This is why we included `fmt.Scanln(&input)`; without it, the program would exit before being given the opportunity to print all the numbers.


```go
// running 10 gorountines
func main() {
  for i := 0; i < 10; i++ {
    go f(i)
  }
  var input string
  fmt.Scanln(&input)
}
```
