# Go Workshop 2023

*Note: These notes might change over time*

###  Before we begin

Compiled vs Intrepred programming language
    Compiled = Code -> Machine code( 1 & 0 ) -> Execute  eg: C/C++ , Go = Faster

    Intrepreted = Code -> Intrepreter -> VM -> Execute eg: Python, PHP , Java ( JIT is shrinking the gap)

Statically vs Dynamically typed

    Statically typed = Type checking in compile time eg: Go

    Dynamically typed = Type checking in runtime time eg: Python

Strongly vs Weakly typed

    Strong = Mixing between unrelated typed is not allowed eg: Go

    Weakly = ixing between unrelated typed is allowed eg: JS (TS)

### What is GO ?

Go is a strongly and statically typed compiled programming language

Go is a very opionated programming langugue, enforced best practices, less error prone, less buggy code

Go was created by Robert Griesemer, Rob Pike, and Ken Thompson.

### Is GO OOP ?

No

OOP = Ineritance, Polymorphism, Abstraction, Encapsluation

### Not in Go ?

No class / sub classes

No while loop

No constructor / de-constructor

No try / catch

### Go vs Other

Go vs Python

buit in concurrency vs import package

Go vs C/C++

Memory mgment

Go vs Java

Less code

### Why use Go ?

Speed, Performance, Concurrency, Reliable etc.

### Variables

1. Int
2. Str
3. Float
4. Bool

4. Array
6. Slice
7. Map

8. Rune
9. Struct

```go
package main

import (
"fmt"
)

func main() {
  var age int = 22 // Integer
  var pi float32 = 3.14 // Floating point number
  var double_float float64 = 3.141562 // Double float
  fmt.Println(age)
  fmt.Println(pi)
  fmt.Println(double_float)
  rune := 'a'
  string_with_single_char := "a"
  string_with_multiple_char := "Prabesh"
  // This prints unicode code point
  fmt.Println(rune)
  // This prints out character
  fmt.Println(string_with_single_char)
  // This prints out string with multiple char
  fmt.Println(string_with_multiple_char)
}
```

### Rune

Rune is a character in go. It is an integer that represents an unicode code point.


```go
package main

func main() {
	name := "Hello"
	name2 := []byte{}
	name2 = append(name2, 72, 119, 108, 108, 111)
	fmt.Println(name)
	fmt.Println((string(name2)))
}
```

### Arithmetics

Some arithmetic operations in go

```go
package main

import (
"fmt"
"math"
)

func main() {
  fmt.Println("Addition", 1+2)
  fmt.Println("Subtraction", 4–3)
  fmt.Println("Multiple", 3*2)
  fmt.Println("Division", 22/7) // This will give output in integer as it is integer operation.
  fmt.Println("Division", 22.0/7) // For floating point operations js8ut add ".0" at end
  fmt.Println("Exponential", math.Pow(20.0, 3))
  fmt.Println("Reminder", 3%2)
  // Boolean operations
  fmt.Println("Greater than", 2 > 1)
  fmt.Println("Greater than", 1 > 2)
  fmt.Println("less than", 1 < 2)
  fmt.Println("Greater or quivalent", 2 >= 1)
  fmt.Println(4.0 == 4)
}
```

### Array

Array are fixed sized groups of variable of same type

`[sizeOfArray]Type`

eg: `var myInts [10]int`

or declare an initialised literal

primes := [10]int{1,2,3,4,5,6,7,8,10}


```go
package main

import (
"fmt"
)

func main() {
  students := [3]string{"prabesh","pradip","asmita"}
  fmt.Println(students)
}
```

### Slices

Slice is a variable-length sequence which stores elements of a similar type

```go
package main

import (
"fmt"
)

func main() {
  // Slice = variable length array
  surnames := []string{} // Declaring slices
  surnames = append(surnames, "Thapa")
  surnames = append(surnames, "Silwal")
  surnames = append(surnames, "Adhikari", "Tamang") // Can append multiple data at once.
  fmt.Println(surnames)
}
```

### Maps

Maps are similar to Javascript objects, python dict or ruby hashes. They are data structure that provide a key->value mapping

The zero value of a map is nil

```go
package main

import (
"fmt"
)

func main() {
  // map[type_of_key]type_of_value
  birthday := map[string]string{
  "name": "prabesh",
  "address": "11 bond str",
  "phn_no": "0414032050",
  }
  fmt.Println(birthday)
  ages := map[string]int{} // defining map without any pre-values
  ages["prabesh"] = 26
  ages["kabita"] = 68
  ages["pradip"] = 21
  ages["prabesh"] = 20
  delete(ages, "prabesh") // delete entry from map
  fmt.Println(ages)
}
```


### Type size

Ints, uints, floats, and complex numbers all have type sizes.


```
int  int8  int16  int32  int64 // whole numbers

uint uint8 uint16 uint32 uint64 uintptr // positive whole numbers

float32 float64 // decimal numbers

complex64 complex128 // imaginary numbers (rare)
```

The size (8, 16, 32, 64, 128, etc) indicates how many bits in memory will be used to store the variable. The default int and uint types are just aliases that refer to their respective 32 or 64 bit sizes depending on the environment of the user.

The standard sizes that should be used unless the developer has a specific need are:

1. int

2. uint

3. float64

4. complex128


### Type conversion

Go does not have type casting, but conversion. Instead of telling the compiler to map a set of bytes to a different representation, the bytes need to be copied to anew memory location for new representation.


```go
i := 42
f := float64(i)
u := uint(f)
```

### Struct

Struct is a typed collection of fields. It is useful in grouping data together to form a new datatype or record.

```go
package main

type Engineer struct {
	Name string
}

func main() {
	engineer := Engineer{"Prabesh"}
	fmt.Println(engineer.Name)
}
```
