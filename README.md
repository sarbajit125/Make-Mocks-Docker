# Make-Mocks-Docker

Make mocks module in docker container. Make Mocks provide an interface to configure and create REAL mocked endpoints for developer till they wait for Real API's.
Inspired from [Mockit](https://github.com/boyney123/mockit)  and developed in NextJS framework and PostgreSQL

## Feature

    1. Live Reload 
    2. Project workspace segregation 
    3. Custom Headers in response
    4. Backup functionality for data migration
    5. Material UI theme

## Getting Started

Make sure you have docker running
    1. Clone this repo
     `git clone --recursive https://github.com/sarbajit125/Make-Mocks-Docker.git`
    2. open the folder in terminal and start the container  
     `cd Make-Mocks-Docker && export DOCKER_BUILDKIT=1 && docker-compose up --build`
    3. Once everything is running you will be able to access ui in this url  
     `http://localhost:8080/`

## Guide

- All routes are grouped according to their domain. For each project you can add a domain subscription in main Dashboard.

- Client ui runs in `http://localhost:8080/`
- Mock server runs in `http://localhost:8080/api/host/*`
- Make sure to append domain name in mock server url  during mocking before each endpoint. For Example: `http://localhost:8080/api/host/paytm/post`  
 Here **paytm** is domain name and **/post** is the endpoint name.
- If you want to check db you can use pgAdmin server running in `http://localhost:5050/`.  
 Credentials are present in docker compose file.
- PostgresSQL server runs by default port in 5040.
- All ports and environment variables can cofigured from docker compose file.

## Updating

- To update Web container without any downtime take latest pull and run following command `docker-compose up -d --build`
- to seed all domains from json use this curl `curl --location 'http://localhost:8080/api/uploadDomains' \
--header 'Authorization: Bearer {{jwtToken}}' \
--form 'routes=@"/Users/comviva/Downloads/MakeMocksBackup/Domains.json"'`
- To seed all routes in a domain from json use this curl `curl --location 'http://localhost:8080/api/uploadRoutes' \
--header 'Authorization: Bearer {{jwtToken}}' \
--form 'routes=@"/Users/comviva/Downloads/MakeMocksBackup/blueMarbale/Routes.json"'`

## Tools

1. [Node(18+)](https://nodejs.org/en/blog/release/v18.14.0)
2. [NPM](https://www.npmjs.com/package/npm)
3. [Docker(4.0+)](https://docs.docker.com/)
4. [NextJs(13)](https://nextjs.org/docs)
5. [Prisma(4.0+)](https://www.prisma.io/docs)
6. [MaterialUI](https://mui.com/material-ui/)
7. [Axios](https://axios-http.com/docs/intro)
8. [PostgresSQL(14-alpine)](https://www.postgresql.org/docs/)
9. [TypeScript](https://www.typescriptlang.org/docs/handbook/intro.html)
10. [PgAdmin](https://www.pgadmin.org/)

## Contributing

If you have any questions, features or issues please raise any issue or pull requests you like.
