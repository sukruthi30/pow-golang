
# Simple Blockchain in Go

This is a basic implementation of a blockchain in Go. It includes a simple web server that allows you to view the current state of the blockchain and add new blocks by sending HTTP requests.

## Features

- **Blockchain Structure:** The blockchain is represented as a series of blocks, with each block containing an index, timestamp, data, hash, previous hash, difficulty, and nonce.

- **Proof of Work:** Blocks are added to the blockchain using a proof-of-work mechanism. The `generateBlock` function mines a new block by repeatedly adjusting the nonce until a hash with the required number of leading zeros (difficulty) is found.

- **Web Server:** The application includes a web server that exposes two endpoints:
  - `GET /`: Retrieves the current state of the blockchain.
  - `POST /`: Adds a new block to the blockchain. The data for the new block is provided in the request body as JSON.

- **Concurrency:** The use of mutexes ensures that block creation and blockchain modification operations are atomic, preventing race conditions.

## Prerequisites

- [Go](https://golang.org/doc/install) installed on your machine.

## Getting Started

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/your-repository.git
   ```

2. Navigate to the project directory:

   ```bash
   cd your-repository
   ```

3. Create a `.env` file in the project root and set the `PORT` variable:

   ```plaintext
   PORT=8080
   ```

4. Run the application:

   ```bash
   go run main.go
   ```

   This will start the web server, and you can access the blockchain at `http://localhost:8080`.

## Adding a Block

To add a new block to the blockchain, you can use a tool like [curl](https://curl.se/) or [Postman](https://www.postman.com/) to send a POST request to `http://localhost:8080` with a JSON payload in the request body. For example:

```bash
curl -X POST -H "Content-Type: application/json" -d "{\"name\": \"75\"}" http://localhost:8080
```

This will add a new block with data `75` to the blockchain.

## Proof of Block being added after the work is done
![Proof of Block being added after the work is done](https://github.com/sukruthi30/pow-golang/blob/master/Screenshot%20(69).png)
