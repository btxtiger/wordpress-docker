# WordPress Docker

This project provides a Docker-based environment for deploying WordPress, MariaDB, phpMyAdmin, and Filebrowser.

## Prerequisites

- Docker
- Docker Compose

## Installation

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd wordpress-docker
   ```

2. Create a `.env` file based on the `.env.example`:
   ```bash
   cp .env.example .env
   ```

3. Update the environment variables in the `.env` file to suit your requirements.

4. Start the containers:
   ```bash
   docker-compose up -d
   ```

## Services

### WordPress
- URL: `http://<WP_DOMAIN>` (defined in `.env`)
- Connected to the MariaDB database.

### phpMyAdmin
- URL: `http://<PMA_DOMAIN>` (defined in `.env`)
- Provides a web interface to manage the MariaDB database.

### Filebrowser
- URL: `http://<FILES_DOMAIN>` (defined in `.env`)
- Default credentials: `admin` / `admin`
- **Important:** Change the default password after the first login to ensure security.

   To change the password:
   1. Log in with the default credentials.
   2. Navigate to the settings and update the password.

## Volumes

- MariaDB data: `db_volume`
- WordPress data: `wp_volume`

## Configuration

### PHP Settings
PHP configuration for WordPress can be customized in the `docker/wp.php.ini` file.

### Networks
This setup uses two networks:
- `app`: Internal network for service communication.
- `main-nginx-proxy`: External network for communication with a reverse proxy.

## License

This project is licensed under the [MIT License](LICENSE).
