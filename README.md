# KoinX Backend Internship Assignment

## Overview

This project is a Node.js application that fetches and stores cryptocurrency data, and provides APIs for retrieving statistics and calculating standard deviation. It was developed as part of the KoinX Backend Internship assignment.

**Live Demo:** [https://koinx-backend-assignment.onrender.com](https://koinx-backend-assignment.onrender.com)

## Features

1. Background job to fetch and store cryptocurrency data every 2 hours.
2. API endpoint to retrieve the latest price, market cap, and 24-hour change for a specified cryptocurrency.
3. API endpoint to calculate the standard deviation of the price for the last 100 records of a specified cryptocurrency.

## Technologies Used

- Node.js
- Express.js
- MongoDB
- Mongoose
- Axios
- node-cron

## Prerequisites

- Node.js (v14 or later)
- MongoDB

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/T1A0R3S2H/KoinX-assignment.git
   cd koinx-backend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create a `.env` file in the root directory and add the following:
   ```
   MONGODB_URI=mongodb://localhost:27017/koinx
   PORT=3000
   ```
   Replace the MONGODB_URI with your actual MongoDB connection string if using a cloud service.

## Running the Application

To start the server:

```
npm start
```

For development with auto-restart on file changes:

```
npm run dev
```

## API Endpoints

1. Get Latest Cryptocurrency Stats
   - Endpoint: `GET /api/stats`
   - Query Parameter: `coin` (bitcoin, matic-network, or ethereum)
   - Example: `https://koinx-assignment-zkwq.onrender.com/api/stats?coin=bitcoin`

2. Get Price Standard Deviation
   - Endpoint: `GET /api/deviation`
   - Query Parameter: `coin` (bitcoin, matic-network, or ethereum)
   - Example: `https://koinx-assignment-zkwq.onrender.com/api/deviation?coin=bitcoin`

## Project Structure

```
project-root/
├── src/
│   ├── app.js
│   ├── config/
│   │   └── database.js
│   ├── models/
│   │   └── Cryptocurrency.js
│   ├── routes/
│   │   └── api.js
│   ├── controllers/
│   │   ├── statsController.js
│   │   └── deviationController.js
│   ├── services/
│   │   └── cryptoService.js
│   └── utils/
│       └── standardDeviation.js
├── .env
├── .gitignore
├── package.json
└── README.md
```

## Background Job

The application uses a cron job to fetch cryptocurrency data every 2 hours. This job updates the database with the latest price, market cap, and 24-hour change for Bitcoin, Matic, and Ethereum.

## Error Handling

The API endpoints include error handling for cases such as:
- Missing coin parameter
- No data found for the specified coin
- Internal server errors

## Deployment

This application is deployed on Render. You can access the live version at:

[Render Deployed Link](https://koinx-assignment-zkwq.onrender.com)

To test the API endpoints, you can use the following URLs:

- Stats API: `https://koinx-assignment-zkwq.onrender.com/api/stats?coin=bitcoin`
- Deviation API: `https://koinx-assignment-zkwq.onrender.com/api/deviation?coin=bitcoin`

Replace `bitcoin` with `matic-network` or `ethereum` to get data for other cryptocurrencies.

Project Link: [GitHub Repo](https://github.com/T1A0R3S2H/KoinX-assignment)
Deployed Link: [Link](https://koinx-assignment-zkwq.onrender.com)
