# RabbitMQ Docker Compose Setup

This repository contains a Docker Compose configuration for setting up a RabbitMQ message broker in a Docker environment. RabbitMQ is a widely-used open-source message broker that allows you to send and receive messages between different parts of your application.

## Prerequisites

Before you begin, ensure you have the following prerequisites installed on your system:

- Docker: [Installation Guide](https://docs.docker.com/get-docker/)
- Docker Compose: [Installation Guide](https://docs.docker.com/compose/install/)

## Usage

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/samuelkago/awesome-docker-compose.git
   cd RabbitMQ
   ```

2. Customize the RabbitMQ configuration (optional):
   - You can modify the `docker-compose.yml` file to change RabbitMQ settings, such as ports, management interface credentials, or any other configuration specific to your needs.

3. Start the RabbitMQ container by running the following command:

   ```bash
   docker-compose up -d
   ```

   This will start RabbitMQ as a background service. You can use the `-d` flag to run it in detached mode.

4. Access the RabbitMQ Management Interface:
   - Open a web browser and navigate to `http://localhost:15672` or `http://<your-server-ip>:15672` (replace `<your-server-ip>` with the IP address of your server if not running locally).
   - Log in with the following credentials:
     - Username: `my_secret_username`
     - Password: `stong_secret_password`
   - From the management interface, you can monitor queues, exchanges, and manage RabbitMQ settings.

5. You can now use RabbitMQ in your applications to publish and consume messages. Connect to the RabbitMQ server using the specified hostname or IP address and the default port `5672`.

6. To stop and remove the RabbitMQ container, run the following command:

   ```bash
   docker-compose down
   ```

## Configuration

By default, the `docker-compose.yml` file uses the following configuration:

- RabbitMQ container name: `rabbitmq`
- RabbitMQ management interface port: `15672`
- RabbitMQ default credentials:
  - Username: `guest`
  - Password: `guest`

You can modify these values by editing the `docker-compose.yml` file to suit your requirements. For production use, it is essential to set secure credentials and adjust other configuration settings as needed.

## Data Persistence

Data stored by RabbitMQ, such as queues and exchanges, are persisted within the container. If you need data persistence, consider using a volume to map RabbitMQ data directories to the host machine.

## Important Notes

- For production deployments, secure RabbitMQ with strong passwords, configure access controls, and consider using SSL/TLS encryption for data transmission.
- Refer to the official [RabbitMQ documentation](https://www.rabbitmq.com/documentation.html) for more advanced configuration options, best practices, and usage instructions.
