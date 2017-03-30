## Development

### API
https://github.com/jacobmoe/resistr-api

#### Prerequisites
- [PostgreSQL](https://www.postgresql.org/)
- [Nodejs](https://nodejs.org/) > 7.0

#### Build

Install the project

```shell
git clone https://github.com/jacobmoe/resistr-api.git

cd resistr-api
npm install 

cp config/production.json.example config/production.json
cp env/secrets.sh.example env/secrets.sh
```

Update `env/secrets.sh`

- [Google Civic Information API](https://console.developers.google.com/apis/credentials)
- [Mapzen](https://mapzen.com/dashboard)

Create a `JWT_SECRET`

```shell
node -e "console.log(require('crypto').randomBytes(32).toString('hex'));"
```

Setup the database

```shell
make db.create
make db.migrate
make db.seed 
```

Run the server
```shell
NODE_ENV=development make
```

#### Tests
```shell
make test
```

### UI
#### Prerequisites
- [Nodejs](https://nodejs.org/)

Install the project

```shell
git clone https://github.com/jacobmoe/resistr-ui.git

cd resistr-ui
npm install 
```

Run the development server

```shell
make
```
