docker run --name postgres -p 5432:5432 -e POSTGRES_PASSWORD=postgres -d postgres:14-alpine
docker exec -it postgres psql -U postgres

migrate create -ext sql -dir db/migration -seq initial_tables

createdb --username=postgres --owner=postgres go_finance
