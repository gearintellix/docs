In golang you can documenting your public function, variable, constant, etc

i still didn't know how making godoc standard formating
but this formating was clean and readable.

## 1. Function

```go
// <function_name> : <function_description>
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

// BoolToString : Convert Bool to String
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

// Users : Users lists
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

references:
 - https://blog.golang.org/godoc-documenting-go-code
