# Distributed Calculator System

## Overview

This project implements a distributed calculator system using a client-server architecture with an optional proxy. The system allows clients to send mathematical expressions to the server, which then computes the result and returns it to the client. The project includes the following components:

- **Server**: Receives and processes calculation requests from clients, performing the necessary calculations and returning the results.
- **Client**: Sends mathematical expressions to the server and displays the results.
- **Proxy**: An optional component that can cache responses from the server to reduce computation time for repeated requests.
- **API**: Defines the protocol and data structures used for communication between clients, servers, and proxies.
- **Calculator**: Provides the core functionality for evaluating mathematical expressions.

## Features

- **Expression Parsing and Evaluation**: The system can parse and evaluate complex mathematical expressions, including the use of constants, binary and unary operators, and functions.
- **Caching with Proxy**: The proxy can cache responses from the server to optimize repeated requests, reducing load and improving performance.
- **Step-by-Step Calculation**: Clients can request detailed steps of the calculations performed by the server.
- **Error Handling**: The system handles various types of errors, including client and server errors, and provides appropriate responses.

## Components

- **`server.py`**: Implements the server that listens for incoming requests from clients, processes them, and returns the results.
- **`client.py`**: Implements the client that sends mathematical expressions to the server and displays the received results.
- **`proxy.py`**: Implements the proxy that intermediates between clients and servers, providing caching capabilities to optimize repeated requests.
- **`api.py`**: Defines the communication protocol and data structures used by the client, server, and proxy.
- **`calculator.py`**: Contains the core logic for parsing and evaluating mathematical expressions.

## Getting Started

### Prerequisites

- Python 3.8 or higher.
- Recommended to run on a Linux/Unix environment, but it is compatible with Windows as well.

### Installation

1. **Clone the repository**:
   ```sh
   git clone https://github.com/yourusername/distributed-calculator.git
   cd distributed-calculator
   ```

2. **Install dependencies** (if any):
   ```sh
   pip install -r requirements.txt
   ```

### Running the System

#### Starting the Server

To start the server:

```sh
python server.py --host <server_host> --port <server_port>
```

- `<server_host>`: The hostname or IP address the server will listen on (default: `127.0.0.1`).
- `<server_port>`: The port number the server will listen on (default: `9997`).

#### Starting the Proxy (Optional)

To start the proxy:

```sh
python proxy.py --proxy_host <proxy_host> --proxy_port <proxy_port> --server_host <server_host> --server_port <server_port>
```

- `<proxy_host>`: The hostname or IP address the proxy will listen on (default: `127.0.0.1`).
- `<proxy_port>`: The port number the proxy will listen on (default: `9998`).
- `<server_host>`: The hostname or IP address of the server to forward requests to (default: `127.0.0.1`).
- `<server_port>`: The port number of the server to forward requests to (default: `9997`).

#### Running the Client

To run the client:

```sh
python client.py --host <server_or_proxy_host> --port <server_or_proxy_port>
```

- `<server_or_proxy_host>`: The hostname or IP address of the server or proxy to connect to (default: `127.0.0.1`).
- `<server_or_proxy_port>`: The port number of the server or proxy to connect to (default: `9997`).

### Example Usage

1. **Start the server**:
   ```sh
   python server.py
   ```

2. **Start the proxy (optional)**:
   ```sh
   python proxy.py
   ```

3. **Run the client and send a request**:
   ```sh
   python client.py
   ```

   The client will send a predefined expression to the server or proxy and display the result.

### Expression Examples

The client can be configured to send different mathematical expressions. Here are some examples:

- Expression: `3 + ((4 * 2) / ((1 - 5) ** (2 ** 3)))`
- Result: `3.0001220703125`

- Expression: `max(2, (3 * 4), log(e), (6 * 7), (9 / 8))`
- Result: `42`

### Contributing

Contributions are welcome! Please fork the repository and submit a pull request. For major changes, please open an issue first to discuss what you would like to change.

### License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

