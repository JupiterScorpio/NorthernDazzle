# D1 NorthDazzle Demo


## What we use

- Cloudflare  for computing
- [D1] for database
- [Typescript](https://www.typescriptlang.org/) for better Javascript
- [Tailwind CSS](https://tailwindcss.com/) for the UI
- [React](https://reactjs.org/) for DOM interaction
- [React Router v7](https://reactrouter.com/home) for the React framework

## Get the demo running
```

### Install packages

```
npm install
```

### Creating the database

```
npm run remote:new
```

Get the output database id and add it to worker/wrangler.jsonc

```
"d1_databases": [
    {
      "binding": "DB",
      "database_name": "northwind",
      "database_id": "..."
    }
  ]
```

### Importing the database

```
npm run remote:init
npm run remote:load
```

## React application

Northwind is a React application. The source code is in the [app folder](./src) folder.

To build a new version run:

```
npm run build
```

To run the dev server, run:

```
npm run dev
```

## Local development

This project supports local development:

```
npm run local:init -w worker
npm run local:load -w worker
npm run dev
```

This will start the application at `http://127.0.0.1:5173` with the database loaded with data.

Wrangler will persist a local SQLite compatible sql file which you can access to with other clients:

```
sqlite3 src/.wrangler/state/v3/d1/*/db.sqlite
.tables
```

## Deploying

Deploy to production when you're done.

```
npm run deploy
```
