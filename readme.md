# Database Experiment

This project is focused on exploring several database systems to understand their functionalities, interfaces, and integration with Python. 

## Objectives

For each database, the following aspects will be explored:

1. **Local Setup**

   * Spin up a Docker container version of the database.
   * Enable the database’s web UI service (if available) for easier exploration.

2. **Exploration via Web UI**

   * Access the database through its web interface.
   * Explore schemas, tables, and data visually.

3. **Command-Line Interface (CLI)**

   * Connect to the database using CLI.
   * Manage users and permissions.
   * Run basic database commands.

4. **Python Integration**

   * Connect to the database using Python libraries (e.g., `sqlalchemy`, `psycopg2`, `mysql-connector`, etc.).
   * Perform data operations:

     * Read and write data.
     * Create, modify, and drop databases/tables.
     * Execute queries programmatically.

     When you connect to any database or data warehouse from Python, what happens is:

      We initialize a client/connection object

      Example: `psycopg2.connect(...)`, `bigquery.Client()`, `snowflake.connector.connect(...)` 
      
      The object represents your session with the database

      We can call methods on it to:
      - Run queries (cursor.execute(), client.query())
      - Fetch results (fetchall(), to_dataframe())
      - Insert/update data
      - Manage transactions

      It abstracts the communication layer whether it’s SQL over TCP, REST API, etc.

## Some Interesting point

### Open-source vs Vendor

PostgreSQL is open-source, while MongoDB, is owned and developed by MongoDB Inc. under the Server Side Public License (SSPL).

Any cloud provider (AWS, GCP, Azure, etc.) can offer “real PostgreSQL” as a managed service (e.g., AWS RDS for Postgres).

The SSPL restricts cloud providers from offering MongoDB as a managed service without open-sourcing their entire service stack.

This means cloud vendors can’t just run “real MongoDB” and sell it the way they can with Postgres. AWS tried to sidestep this by creating Amazon DocumentDB, which is “MongoDB-compatible” but not the real engine.