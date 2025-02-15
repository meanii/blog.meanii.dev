# Ghost Blog Platform Setup for blog.meanii.dev

This repository contains the necessary files to set up the Ghost blog platform for `blog.meanii.dev` using Docker and Nginx. Below are the steps to get your Ghost blog up and running.

## Prerequisites

- Docker installed on your machine.
- Docker Compose installed on your machine.
- Basic understanding of Docker and Docker Compose.
- A domain name (`blog.meanii.dev`) pointed to your server's IP address (if deploying publicly).

## Setup Instructions

1. **Clone the Repository**

    ```bash
    git clone https://github.com/meanii/blog.meanii.dev.git
    cd blog.meanii.dev
    ```

2. **Customize Site Header and Footer**

    Edit the `config/site-header.html` and `config/site-footer.html` files to include your custom HTML snippets for the site header and footer.

3. **Configure Nginx**

    The `./nginx.conf` file is pre-configured to reverse proxy requests to the Ghost application. You can modify it if you have specific Nginx requirements.

4. **Start the Services**

    Use Docker Compose to start the Ghost and Nginx services.

    ```bash
    docker compose up -d
    ```

    This command will start the following services:

    - Ghost blog application
    - MySQL database
    - Nginx reverse proxy

5. **Access the Ghost Blog**

    Once the services are up and running, you can access the Ghost blog at:

    ```
    http://localhost:2368
    ```

    The Nginx reverse proxy will also be available at:

    ```
    http://localhost:80
    ```

6. **Admin Dashboard**

    To access the Ghost admin dashboard, navigate to:

    ```
    http://localhost:2368/ghost
    ```

    Follow the on-screen instructions to complete the setup and create your first blog post.

## Stopping the Services

To stop the services, run:

```bash
docker compose down
```

## Troubleshooting

- **Port Conflicts**: Ensure that ports `2368` and `80` are not in use by other services on your machine.
- **Database Issues**: If the Ghost application fails to connect to the MySQL database, double-check the environment variables in the `.env` file.
- **Nginx Configuration**: If you encounter issues with the Nginx reverse proxy, review the `nginx.conf` file for any misconfigurations.

## Customization

- **Ghost Theme**: You can customize the Ghost theme by placing your theme files in the `content/themes/` directory.
- **Nginx Configuration**: Modify the `nginx.conf` file to add SSL, custom routing, or other Nginx-specific configurations.
