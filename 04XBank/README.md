# XBank [Golang + Postgres + gRPC + Kubernetes]

## Setup


### Tools 
 - Docker
 - Postgres
 - TablePlus/Azure Data Studio
 - [Golang Migrate](https://github.com/golang-migrate/migrate)
   ```shell
   brew install golang-migrate
   ```
 - [sqlc](https://sqlc.dev/)
 - https://docs.sqlc.dev/en/latest/tutorials/getting-started-postgresql.html 
   ```shell 
   brew install sqlc
   ```
 - [Golang Postgres Driver for database/sql](https://github.com/lib/pq)


### Section 1 Highlights
 - ACID Properties [Read More here](https://www.databricks.com/glossary/acid-transactions)
   <br><img src="assets/db_acid.png" alt="image" width="400" height="auto">
 - DB Schema can be created using dbdiagram.io
   <br><img src="assets/db_schema.png" alt="image" width="400" height="auto">
 - Docker, Postgres(Docker Version), TablePlus or Azure Data Studio Installation
 - `sqlc` can be used to generate the Golang Code (check db/query folder for sql queries and db/sqlc for generated Golang code)
 - Added Unit Tests for all CRUD operations (Accounts, Entries, Transfers TABLES)
 - What is a DB Transaction
   - A transaction in SQL is a sequence of one or more operations such as insertions, updates, or deletions, performed on a database as a single unit of work.
   <img src="assets/db_transaction.png" alt="image" width="380" height="auto">
   <img src="assets/transaction_example.png" alt="image" width="380" height="auto">
 - Deadlock can occur while executing the transactions<br>
   <img src="assets/transaction_deadlock_queries.png" alt="image" width="440" height="auto"> 
   <img src="assets/transaction_deadlock_shell.png" alt="image" width="440" height="auto"> 
 - Transaction Isolation Levels (ACID)
   [TODO: Revisit the Transaction Isolation videos once]
 - Different Read phenomenon<br>
     <img src="assets/read_phenomena.png" alt="image" width="380" height="auto">
 - Transaction Isolation Levels<br>
     <img src="assets/isolation_levels.png" alt="image" width="380" height="auto">
 - Postgres Isolation Levels<br>
     <img src="assets/pg_isolation_levels.png" alt="image" width="380" height="auto">

 - GitHub Actions - CI/CD platform that allows you to automate build, test and deployment pipelines
   - WorkFlows can be created using GitHub Actions. 
     - WorkFlow is an automated procedure which is made up of 1+ Jobs  
     - can be triggered by Events, Scheduled or Manually
   - Created a GitHub Action for running tests automatically everytime new changes are pushed.(checkout `.github/workflows/xbank.yml` for more details)

### Section 2 Highlights
  - Started with implementation of RESTful HTTP apis using Gin Web Framework. And created APIs for CreateAccount, GetAccount, ListAccounts
  - Added Viper support for loading Configs
    <img src="assets/why_viper.png" alt="image" width="380" height="auto">
