# README

## dockerの動かし方

`docker-compose build`
`docker-compose up`

`docker-compose run api rails g scaffold User name:string email:string`
`docker-compose run api rails db:create`
`docker-compose run api rails db:migrate`

`docker-compose down`

