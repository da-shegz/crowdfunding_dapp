# Decentralized Crowdfunding DApp

This is a simple decentralized crowdfunding application built using Cartesi. It allows users to create crowdfunding campaigns, contribute funds to active campaigns, and inspect the status of campaigns.

## Features

1. **Create Campaign**: Users can create a new crowdfunding campaign with a target amount.
2. **Contribute to Campaign**: Users can contribute funds to an existing campaign.
3. **Inspect Campaigns**: Users can view the current status and details of all campaigns.

## Prerequisites

- Node.js and npm
- Cartesi Rollups server

## Setup

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/crowdfunding-dapp.git
   cd crowdfunding-dapp
   ```

2. **Install Dependencies**

   ```bash
   npm install
   ```

3. **Set Up Environment Variables**

   Create a `.env` file in the root directory and add the following environment variables:

   ```env
   ROLLUP_HTTP_SERVER_URL=http://your-rollup-server-url
   ```

   Replace `http://your-rollup-server-url` with the URL of your Cartesi Rollups server.

## Running the DApp

Start the application using:

```bash
node index.js
```

The application will start and continuously poll the Cartesi Rollups server for requests.

## API Endpoints

- **Create Campaign**

  - **Action**: `create`
  - **Payload Example**:

    ```json
    {
      "action": "create",
      "campaignId": "campaign1",
      "description": "Help us build a new community center",
      "targetAmount": 10000
    }
    ```

- **Contribute to Campaign**

  - **Action**: `contribute`
  - **Payload Example**:

    ```json
    {
      "action": "contribute",
      "campaignId": "campaign1",
      "amount": 500
    }
    ```

- **Inspect Campaigns**

  - **Route**: `campaigns`
  - **Payload Example**:

    ```json
    {
      "payload": "campaigns"
    }
    ```

## How It Works

1. **Create Campaign**: Adds a new crowdfunding campaign with a description, target amount, and initializes it with zero raised amount and an empty list of contributors.
2. **Contribute to Campaign**: Updates the raised amount of a campaign and records the contributor's details.
3. **Inspect Campaigns**: Provides details of all campaigns including their current status, target amount, raised amount, and contributors.
