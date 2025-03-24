# Contact Support Microservice

This Docker image provides a microservice for handling contact messages and form submissions. It allows retrieving a contact message and submitting a contact form.

## Usage

To run a container from this image, use the following command:

```bash
docker run -p 8000:8000 contact-support-microservice
```

The microservice will be accessible at `http://localhost:8000`.

### API Endpoints

- `GET /api/contact-message`: Retrieves a contact message.
- `POST /api/contact-submit`: Submits a contact form.

## Environment Variables

This microservice does not require any environment variables to be set.

## Volumes

This microservice does not use any volumes.

## Docker Network

To enable communication between the Contact Support microservice and other microservices or applications, ensure that the containers are connected to the same Docker network. You can achieve this by following these steps:

1. Create a Docker network:
   ```bash
   docker network create my-network
   ```

2. Run the Contact Support microservice container with the `--network` flag:
   ```bash
   docker run --network my-network -p 8000:8000 contact-support-microservice
   ```

3. Run other microservice or application containers on the same network:
   ```bash
   docker run --network my-network -p 4000:4000 ecommerce-ui
   ```

By connecting the containers to the same Docker network, they can communicate with each other using their container names as hostnames.