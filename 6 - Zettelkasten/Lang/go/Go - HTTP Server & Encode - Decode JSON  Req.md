
2024-09-24 12:13

Status: #child 

Tags: [[go]] [[programming-language]]

# Go - HTTP Server

`http.ListenAndServe` - used to boot up the server for req-res

```go
package main
import (
"log"
"net/http"
)

type server struct {
	addr string
}

func (s *server) ServeHTTP(w http.ResponseWriter, r *http.Request) {
	w.Write([]byte("Helllo from the server"))
}

func main() {
	s := &server{addr: ":8080"}
	
	if err := http.ListenAndServe(s.addr, s); err != nil {
		log.Fatal(err)
	}
}
```
- `struct` is like class in OOP based language
	- Difference is OOP is inheritance oriented, whereas `struct` is composition based
	- `func (s *server)` is called method receiver
		- `ServeHTTP` - satisfies gos interface of net/http, it is needed or we cannot use it where the function expects the similar interface
	- `s := &server{addr: ":8080}` -> we are instantiating the struct

***

```go
package main
import (
"net/http"
)

type api struct {
	addr string
}

func (s *api) ServeHTTP(w http.ResponseWriter, r *http.Request) {
	switch r.Method {
	case http.MethodGet:
		switch r.URL.Path {
		case "/":
			w.Write([]byte("GET Method"))
		case "/index":
			w.Write([]byte("GET index"))
		}
		
	case http.MethodPost:
		w.Write([]byte("POST method"))
	default:
		w.Write([]byte("Error 404"))
	}
}

func main() {
	api := &api{addr: ":8080"}
	srv := &http.Server{
		Addr: api.addr,
		Handler: api,
	}
	srv.ListenAndServe()
}
```

- The reason refactored version is instantiated with `http.Server` is  to add configs, also we must pass the entire object to the `Handler` in `http.Server`, not the method itself

***

```go
package main
import (
"net/http"
)

type api struct {
	addr string
}

func (s *api) getUsersHandler(w http.ResponseWriter, r *http.Request) {
	w.Write([]byte("GET Users"))
}

func (s *api) postUsersHandler(w http.ResponseWriter, r *http.Request) {
	w.Write([]byte("POST Users"))
}

func main() {
	api := &api{addr: ":8080"}
	mux := http.NewServeMux()
	srv := &http.Server{
		Addr: api.addr,
		Handler: mux,
	}
	
	mux.HandleFunc("GET /users", api.getUsersHandler)
	mux.HandleFunc("POST /users", api.postUsersHandler)
	
	srv.ListenAndServe()
}
```
- mux is called multiplexer in cs
- mux is used for routing here in a clean fashion
- `mux := http.NewServeMux()` - returns a pointer to `ServeMux` struct



# Go - Encode (Marshelling) - Decode(Unmarshelling) Req & Res
- In Go, JSON marshalling is the process of converting a data structure (such as a struct or a slice) into a JSON string using the `json.Marshal` function. Unmarshalling is the reverse process, converting a JSON string into a data structure using the `json.Unmarshal` function.


```go
// user.go
package main

  

type User struct {
	FirstName string `json:"first_name"`
	LastName string `json:"last_name"`
}
```

- `json:"first_name"` - is called *struct tags* which is used for labelling the json request and response herein the case for JSON specific case
- Struct tags provide metadata about a field that can be used by the reflection package or other libraries at runtime.

```go
// api.go
package main

import (
	"encoding/json"
	"errors"
	"net/http"
)

type api struct {
	addr string
}

var users = []User{}

func (s *api) getUsersHandler(w http.ResponseWriter, r *http.Request) {
	w.Header().Set("Content-Type", "application/json")

	// encode users slice to json
	err := json.NewEncoder(w).Encode((users))

	if err != nil {
		http.Error(w, err.Error(), http.StatusInternalServerError)
		return
	}

	w.WriteHeader(http.StatusOK)
}

func (s *api) postUsersHandler(w http.ResponseWriter, r *http.Request) {

	// decode the json to proper data structure
	var payload User
	err := json.NewDecoder(r.Body).Decode(&payload)

	if err != nil {
		http.Error(w, err.Error(), http.StatusBadRequest)
		return
	}

	u := User{
		FirstName: payload.FirstName,
		LastName:  payload.LastName,
	}

	if err = insertUser(u); err != nil {
		http.Error(w, err.Error(), http.StatusBadRequest)
		return
	}

	w.WriteHeader(http.StatusCreated)
}

func insertUser(u User) error {
	// input validation
	if u.FirstName == "" {
		return errors.New("first name is required")
	}

	if u.LastName == "" {
		return errors.New("first name is required")
	}

	// storage validation
	for _, user := range users {
		if user.FirstName == u.FirstName && user.LastName == u.LastName {
			return errors.New("User already exists")
		}
	}

	users = append(users, u)

	return nil
}

```

# References

https://www.youtube.com/watch?v=xotJaM9koWo




