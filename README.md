# Docker Compose Configuration for Typesense

This `compose.yaml` file defines a Docker Compose configuration for running a Typesense search engine instance.

## Service: typesense

### Image
- Uses the official Typesense image: `typesense/typesense:0.25.2`

### Restart Policy
- Set to `on-failure`, meaning the container will restart if it exits due to an error

### Port Mapping
- Maps host port 8108 to container port 8108
- Allows access to Typesense API from the host machine

### Volume
- Mounts a local directory `./typesense-data` to `/data` in the container
- Ensures data persistence across container restarts

### Command
- Specifies runtime configuration for Typesense:
  - `--data-dir /data`: Sets the data directory to `/data`
  - `--api-key=your-secret-api-key`: Sets the API key for authentication
  - `--enable-cors`: Enables Cross-Origin Resource Sharing (CORS)

## Usage
To start the Typesense service:
1. Ensure Docker and Docker Compose are installed on your system
2. Navigate to the directory containing this `compose.yaml` file
3. Run `docker-compose up -d` to start the service in detached mode

Note: Keep the API key secure and do not share it publicly.
