

---

# WebSocket Testing Project

This project is designed to test WebSocket interactions and ensure their correct functionality in a multi-user environment. The tests include scenarios such as user joining, movement within defined boundaries, and broadcasting events across WebSocket connections.

## Features

- Simulates multiple WebSocket connections.
- Tests:
  - Joining a space and acknowledging the join.
  - Validating user movement within boundaries.
  - Broadcasting movement to other connected clients.
  - Handling user disconnections gracefully.

## Prerequisites

- Node.js (v14+ recommended)
- NPM or Yarn
- Backend WebSocket server running and accessible at the specified `WS_URL`.
- Axios for HTTP requests.

## Setup

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   - Create a `.env` file in the root directory.
   - Add the following variables:
     ```
     BACKEND_URL=<your_backend_url>
     WS_URL=<your_websocket_url>
     ```

4. Run the tests:
   ```bash
   npm test
   ```

## Testing

The project uses Jest for testing WebSocket interactions. The tests are located in the `tests` folder and cover various scenarios to validate WebSocket behavior.

### Troubleshooting WebSocket Issues

If WebSocket is not reachable during tests:
- Ensure the backend WebSocket server is running and reachable at the URL specified in the `.env` file.
- Mock WebSocket globally for Jest by adding the following in `jest.setup.js`:
  ```javascript
  global.WebSocket = require('ws');
  ```

- Update the `jest.config.js` file to include the setup file:
  ```javascript
  module.exports = {
    setupFiles: ['./jest.setup.js'],
    // other Jest configurations
  };
  ```

## Contributing

Feel free to fork the repository and submit pull requests. Contributions are welcome!

## License

This project is licensed under the MIT License.

---

