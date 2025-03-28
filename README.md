# K2 Task Tracker API

## Project Overview

K2 Task Tracker is a backend service for tracking and managing tasks within the KOII Network ecosystem. This service provides a robust API for monitoring, submitting, and managing blockchain-related tasks and activities.

### Key Features
- Task tracking and management
- Whitelisted task monitoring
- Public key and staking key utilities
- Blockchain-compatible task submission handling

## Getting Started

### Prerequisites
- Node.js (v14+ recommended)
- Yarn or npm
- MongoDB
- Docker (optional)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/your-repo/k2-task-tracker.git
cd k2-task-tracker
```

2. Install dependencies:
```bash
yarn install
# or
npm install
```

3. Configure environment variables:
Copy `.env.example` to `.env` and fill in the necessary configurations:
```bash
cp .env.example .env
```

4. Start the development server:
```bash
yarn start
# or
npm start
```

## API Documentation

### Endpoints

#### 1. Task Submission
- **Method**: POST
- **Path**: `/submit-task`
- **Description**: Submit a new task to the network
- **Request Body**:
```json
{
  "taskId": "string",
  "publicKey": "string",
  "data": "object"
}
```
- **Response**:
```json
{
  "success": true,
  "message": "Task submitted successfully"
}
```

#### 2. Get Active Whitelisted Tasks
- **Method**: GET
- **Path**: `/active-tasks`
- **Description**: Retrieve currently active whitelisted tasks

## Authentication

The API uses public key authentication. Ensure you provide a valid public key with appropriate permissions when making requests.

## Project Structure

```
k2-task-tracker/
├── helperFunctions/         # Utility functions
│   ├── activeWhitelistedTasks.js
│   ├── schema.js
│   └── stakingKeyToPublicKey.js
├── index.js                 # Main application entry
└── package.json             # Project metadata and dependencies
```

## Technologies Used

- Express.js - Web framework
- Mongoose - MongoDB object modeling
- @_koi/web3.js - Blockchain interactions
- Node-cron - Scheduled tasks
- Dotenv - Environment configuration

## Deployment

### Docker Deployment
```bash
# Build Docker image
yarn dockerize

# Or manually
docker build . -t k2-task-tracker
docker run -p 3000:3000 k2-task-tracker
```

### Environment Considerations
- Use environment variables for sensitive configurations
- Ensure MongoDB connection is secure
- Configure appropriate network and firewall rules

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

Maintained by [KOII Network](https://koii.network)