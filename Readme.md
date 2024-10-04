# Payment Link Application

A web-based application that integrates Stripe for payment processing. It features a React frontend, Flask backend, and MongoDB for data storage. The application allows users to generate payment links and test Stripe payments in a development environment using Ngrok to expose the local server.

## Table of Contents

- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [Backend (Flask)](#backend-flask)
  - [Frontend (React)](#frontend-react)
  - [Exposing Local Server with Ngrok](#exposing-local-server-with-ngrok)
- [Usage](#usage)
- [Features](#features)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Contributors](#contributors)
- [License](#license)

## Tech Stack

- **Frontend**: React
- **Backend**: Flask
- **Database**: MongoDB
- **Payment Processing**: Stripe
- **AI Tools**: OpenAI GPT-4 (for development assistance)

## Prerequisites

Ensure the following tools are installed before setting up the project:

- **Node.js** (for the React frontend)
- **Python** (for the Flask backend)
- **MongoDB** (for the database)
- **Ngrok** (for exposing your local server to the internet)

## Installation

### Backend (Flask)

1. **Clone the Backend Repository**:
    ```bash
    git clone <backend-repo-url>
    cd <backend-directory>
    ```

2. **Create a Virtual Environment**:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Set Environment Variables**:
    Create a `.env` file in the backend directory with the following content:
    ```plaintext
    STRIPE_API_KEY=your_stripe_api_key
    MONGO_URI=mongodb://localhost:27017/yourdatabase
    ```

5. **Run the Flask Application**:
    ```bash
    flask run
    ```
    The backend will be accessible at `http://localhost:5000`.

### Frontend (React)

1. **Clone the Frontend Repository**:
    ```bash
    git clone <frontend-repo-url>
    cd <frontend-directory>
    ```

2. **Install Dependencies**:
    ```bash
    npm install
    ```

3. **Start the React Application**:
    ```bash
    npm start
    ```
    The frontend will be accessible at `http://localhost:3000`.

### Exposing Local Server with Ngrok

To expose your Flask backend to the internet for testing Stripe payments:

1. **Run Ngrok**:
    In a new terminal window, run:
    ```bash
    ngrok http 5000
    ```

2. **Note** the public URL Ngrok provides. This URL will tunnel to your local server and can be used for webhooks or testing internet-facing features like Stripe payments.

## Usage

- Open your web browser and navigate to `http://localhost:3000` to start using the Payment Link Application.
- For testing Stripe payments, use the Ngrok URL (e.g., for setting up webhooks) provided when you expose your backend.

## Features

- **Payment Processing**: Integrates Stripe for creating and processing payments.
- **Frontend**: Responsive React UI for user interaction.
- **Backend**: Flask API to manage payment link creation and transaction data.
- **Database**: MongoDB for persistent storage.
- **Ngrok**: Tunnel the local backend server for external access during development.

## Configuration

Ensure you set up the following environment variables in the `.env` file in your backend directory:

- `STRIPE_API_KEY`: Your Stripe API key for processing payments.
- `MONGO_URI`: MongoDB connection string, typically in the format `mongodb://localhost:27017/yourdatabase`.

## Troubleshooting

- **Ngrok Not Working**: Ensure your local backend server is running on the correct port (5000) and you’ve properly installed and configured Ngrok.
- **Stripe Payment Issues**: Verify that your Stripe API key is correct and that webhooks are set up properly using the Ngrok public URL.
- **Frontend Not Loading**: Check the console for any errors and ensure all dependencies are installed correctly with `npm install`.