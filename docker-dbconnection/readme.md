- You can connect docker container with database.
1. docker container with local system database
2. docker container with  docker container database but both container is in same network 
- 1. Docker Container API with Local database
    
    to archive this you need to change some conf files 
    
    first find posetgre.conf file and make this changes
    
    ```bash
    nano /etc/postgresql/10/main/postgresql.conf
    listen_addresses = '*'
    ```
    
    Note down if you make change in any serice you must need to restart that service
    
    now create simple node project to run this
    
    ```tsx
    // it is a simple node app that use localdb and get data
    const http = require('http');
    const { Pool } = require('pg');
    
    // Define PostgreSQL connection configuration
    const pool = new Pool({
      user: 'postgres',
      host: 'localhost',
      database: 'demo',
      password: '123456',
      port: 5432,
    });
    
    // Define port
    const PORT = process.env.PORT || 3005;
    
    // Create HTTP server
    const server = http.createServer(async (req, res) => {
      // Set response status and headers
      res.writeHead(200, { 'Content-Type': 'text/plain' });
    
      try {
        // Connect to PostgreSQL and perform database operations
        const client = await pool.connect();
    
        // Perform database query to retrieve data
        const result = await client.query('SELECT * FROM \"CityMaster\"');
        const data = result.rows;
    
        // Send response body with retrieved data
        res.end(`Data from PostgreSQL: ${JSON.stringify(data)}\n`);
    
        // Release client back to the pool
        client.release();
      } catch (err) {
        console.error('Error executing database query:', err);
        res.end('Error retrieving data from PostgreSQL\n');
      }
    });
    
    // Start the server
    server.listen(PORT, () => {
      console.log(`Server is running on http://localhost:${PORT}`);
    });
    ```
    
    now create its docker file
    
    ```bash
    // dockerfile
    FROM node:20.12.2
    WORKDIR /app
    COPY package*.json ./
    RUN npm install
    COPY . .
    EXPOSE 3005
    CMD ["node", "server.js"]
    
    // docker-compose
    version: '3.9'
    
    services:
      node-server:
        build:
          context: .
          dockerfile: Dockerfile
        ports:
          - "3005:3005"
        restart: always
    ```
    
    its time to create docker image and container
    
    ```bash
    docker build -t test .
    docker run --network=host -p 3005:3005 test
    ```