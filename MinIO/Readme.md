

# Minio Docker Compose Setup

This repository contains a Docker Compose configuration for setting up a Minio object storage server in a Docker environment. Minio is an open-source, self-hosted, and S3-compatible object storage system that allows you to store and manage your data.

## Prerequisites

Before you begin, ensure you have the following prerequisites installed on your system:

- Docker: [Installation Guide](https://docs.docker.com/get-docker/)
- Docker Compose: [Installation Guide](https://docs.docker.com/compose/install/)

## Usage

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/minio-docker-compose.git
   cd minio-docker-compose
   ```

2. Customize the Minio configuration (optional):
   - You can modify the `docker-compose.yml` file to change the environment variables for Minio, such as access keys, secret keys, and the data directory.

3. Start the Minio container by running the following command:

   ```bash
   docker-compose up -d
   ```

   This will start Minio as a background service. You can use the `-d` flag to run it in detached mode.

4. Access the Minio web interface:
   - Open a web browser and navigate to `http://localhost:9000` or `http://<your-server-ip>:9000` (replace `<your-server-ip>` with the IP address of your server if not running locally).
   - You will be prompted to log in with the access and secret keys provided in the `docker-compose.yml` file.

5. You can now use Minio to create buckets, upload, and manage your objects via the web interface or programmatically using the S3 API.

6. To stop and remove the Minio container, run the following command:

   ```bash
   docker-compose down
   ```

## Configuration

By default, the `docker-compose.yml` file uses the following configuration:

- MINIO_ROOT_USER: `my_secret_username`
- MINIO_ROOT_PASSWORD: `stong_secret_password`
- Minio web interface port: `9000`
- Minio data directory: `./data` (mapped to `/data` inside the container)

You can modify these values by editing the `docker-compose.yml` file to suit your requirements.

## Data Persistence

Data stored in Minio is persisted in the `./data` directory on your host machine. This ensures that your data remains intact even after stopping or removing the Minio container.

## Important Notes

- Make sure to secure your Minio instance by changing the access and secret keys in the `docker-compose.yml` file.
- For production use, consider configuring SSL/TLS encryption to secure data transmission.
- Refer to the official [Minio Documentation](https://docs.min.io/) for more advanced configuration options and usage instructions.


