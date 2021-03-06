# Backend Server

## NodeJS

- Run script: `node my-script.js`
- Or run javascript in console: `node`

### Http

- is a built-in module in Node
- is for implementing web servers
- is CommonJS, not ES6 (for now)

## NPM

- Short for "Node Package Manager"
- project root has `package.json`
- semantic versioning
  - `"^4.17.2"`
    - major number (first)
    - minor number (second)
    - patch number (third)
    - caret (^) means minor/patch can be higher,
      but not major

### Dependencies

- Defined in `package.json` in project's root
- To update: `npm update`
- Install all up-to-date dependencies:
  `npm install`

## Express

- is a library that abstracts
  http module
- To install: `npm i express`

## REST

- is an architectural style
- is not a standard in itself
  - but HTTP, URI, JSON, XML, etc. are

### Web Service APIs

- base URI
- HTTP methods
  - GET
    - is safe (read-only)
  - GET, PUT, DELETE
    - are idempotent
      - applying multiple times should be
        the same as applying once
      - POST is not???
  - Cache-able:
    - GET and POST
    - responses can be stored for future use
  - CRUD:
    - GET, PUT, DELETE
    - POST is _not_ CRUD
- media type defining state transitions

## Databases

### MongoDB

- is a Document database
- NoSQL
- Mongoose
  - is a package to use MongoDB easier

## Development Tools

### Nodemon

- auto-restart node app when files change
- to install: `npm i -D nodemon`
- run with: `node_modules/.bin/nodemon index.js`
  - or better: define npm script in `package.json`:
    - ```json
      "scripts": {
        //...,
        "dev": "nodemon index.js"
      }
      ```
    - run with: `npm run dev`

### Rest Clients

- REST Client extension in VS Code
- Postman
