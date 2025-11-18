# Node.js Project

## Prerequisites
- Node.js (v14 or higher)
- npm (Node Package Manager)

## Installation

1. Install dependencies:
```bash
npm install
```

## Running the Project

### Local Development
```bash
npm start
```

The application will start on the configured port (check `index.js` for port details).

### Using Docker

1. Build the Docker image:
```bash
docker build -t nodeproject .
```

2. Run the container:
```bash
docker run -p 3000:3000 nodeproject
```

### Using Docker Compose
```bash
docker-compose up
```

## Project Structure
- `index.js` - Main application file
- `package.json` - Node.js dependencies and scripts
- `Dockerfile` - Docker configuration
- `docker-compose.yml` - Docker Compose configuration
- `MOCK_DATA.json` - Sample data file
