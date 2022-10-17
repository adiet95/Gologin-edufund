# Gologin-edufund
Aim to create login &amp; regist with Go

## 🔗 Description

This Backend Application is used for login & register in this application there are several features such as JWT, Validation email just for checking email type, Testing, Hasing password .etc

I'am using UUID for user_id, don't forget to create extenxion in SQL console after create the database with this query below :
- CREATE EXTENSION IF NOT EXISTS "uuid-ossp";

## Several command you must know in this app :
```bash
1. go run . serve //to run the app / server
2. go run . migrate -u //for database migration
# or
go run . migrate -d //for rollback
3. go run . seed // to seeding data Role admin if u want Email : "admin@gmail.com" Pass : admin12345678
```

## 🛠️ Installation Steps

1. Create Root Directory folder in Gopath 
```
github.com/adiet95/
```

2. Clone the repository in Directory folder that has been created "github.com/adiet95/"
```bash
git clone git@github.com:adiet95/Gologin-edufund.git
```

3. Install dependencies

```bash
go get -u ./...
# or
go mod tidy
```

4. Create New your PostgreSQL database

5. Add Env

```sh
  DB_USER = Your DB User
  DB_HOST = Your DB Host
  DB_NAME = Your DB Name
  DB_PASS = Your DB Password
  JWT_KEYS = Your JWT Key
  PORT = Your Port
```

6. Database Migration and Rollback

```bash
go run main.go migrate --up //for database migration
# or
go run main.go migrate --down //for rollback
```
7. Run the app

```bash
go run . serve
```

## 🔗 RESTful endpoints
### POST /register

> Create new user

_Request Header_
```
not needed
```

_Request Body_
```
{
  "user_name": <your username> (STRING),
  "email": <your email> (STRING),
  "password": <your password> (STRING),
  "address": <your address> (STRING),
  "phone": <your phone> (STRING)
}
```

#### Success Response: ####
_Response (201 - Created)_
```
{
  "id": <id>,
  "user_name": <your username>,
  "email": <your email>,
  "password": <your encrypted password>,
  "address": <your address>,
  "phone": <your phone>,
  "updatedAt": <date>,
  "createdAt": <date>
}
```

### POST /login

> Process Login

_Request Header_
```
not needed
```

_Request Body_
```
{
  "email": <your email> (STRING),
  "password": <your password> (STRING)
}
```

#### Success Response: ####
_Response (200 - Ok)_
```
{
  "token": <your access token>
}
```

## 💻 Built with

- [Golang](https://go.dev/): Go Programming Language
- [gorilla/mux](https://github.com/gorilla/mux): for handle http request
- [Postgres](https://www.postgresql.org/): for DBMS


## 🚀 About Me

- Linkedin : [Achmad Shiddiq](https://www.linkedin.com/in/achmad-shiddiq-alimudin/)
