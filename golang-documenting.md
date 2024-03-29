In golang you can documenting your public function, variable, constant, etc

i still didn't know how making godoc standard formating

but this format was pretty clean and readable.

# Preview

preview tooltips showing on visual studio code

![Image](https://raw.githubusercontent.com/gearintellix/docs/master/assets/Screen%20Shot%202019-06-18%20at%2014.24.17.png)

# Script

## 1. Function

```go
// <function_name> : <function_description>
//
// **@Params:** [ `<parameters_name>`: <parameter_description>; ...n ]
//
// **@Returns:** [ `<return_key>`: <return_description>; ...n ]
func () <function_name> (...) { }


// ============[ or a simpler one ]============


// <function_description_with_contains_name>
//
// **@Params:** [ `<parameters_name>`: <parameter_description>; ...n ]
//
// **@Returns:** [ `<return_key>`: <return_description>; ...n ]
func () <function_name> (...) { }
```

## 2. Type, Variable & Constant

```go
// <name> : <description>
var <name> string


// ============[ or a simpler one ]============


// <description_with_contain_name>
var <name> string
```

# Examples:

## 1. Function

```go
// Int64ToString : Convert Int64 to String
//
// **@Params:** [ `v`: value ]
//
// **@Returns:** [ `$1`: string ]
func Int64ToString(v int64) string {
  return strconv.FormatInt(v, 10)
}

// BoolToString to casting type Bool to String
//
// **@Params:** [ `v`: value ]
//
// **@Returns:** [ `res`: string ]
func BoolToString(v bool) (res string) {
  res = strconv.FormatBool(v)
  return
}

// getRandomString : Get Random String
//
// **@Params:** []
//
// **@Returns:** [ `res`: string; `ok`: is ok? ]
func getRandomString() (res string, ok bool) {
  res = "hello"
  ok = true
}

// void : No params no return
//
// **@Params:** []
//
// **@Returns:** []
func void() {
  fmt.Println("Hello world")
}
```

## 2. Type, Variable & Constant

```go
// Model : Model struct
type Model struct {
}

// Models : Slice Model struct
type Models []Model

// Users lists
var Users Models

// IModel : Model Interface
type IModel interface {
  // TableName : Get Table Name
  //
  // **@Params:** []
  //
  // **@Returns:** [ $1: table name ]
  TableName() string
}

// Operator : Math Operator
type Operator string

const (
  // Add : Add Operator
  Add Operator = "+"
  
  // Subtract : Subtract Operator
  Subtract = "-"
  
  // Multiple : Multiple Operator
  Multiple = "*"
  
  // Divide : Divide Operator
  Divide = "/"
)
```

References:
 - https://blog.golang.org/godoc-documenting-go-code
