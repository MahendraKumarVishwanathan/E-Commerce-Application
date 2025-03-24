# Product Catalog Microservice

This Docker image provides a microservice for managing a product catalog. It allows retrieving all products and fetching a single product by its ID.

## Usage

To run a container from this image, use the following command:

```bash
docker run -p 3001:3001 product-catalog-microservice
```

The microservice will be accessible at `http://localhost:3001`.

### API Endpoints

- `GET /api/products`: Retrieves all products.
- `GET /api/products/:id`: Retrieves a single product by its ID.

## Environment Variables

This microservice does not require any environment variables to be set.

## Volumes

This microservice does not use any volumes.

## Docker Network

To enable communication between the Product Catalog microservice and other microservices or applications, ensure that the containers are connected to the same Docker network. You can achieve this by following these steps:

1. Create a Docker network:
   ```bash
   docker network create my-network
   ```

2. Run the Product Catalog microservice container with the `--network` flag:
   ```bash
   docker run --network my-network -p 3001:3001 product-catalog-microservice
   ```

3. Run other microservice or application containers on the same network:
   ```bash
   docker run --network my-network -p 4000:4000 ecommerce-ui
   ```

By connecting the containers to the same Docker network, they can communicate with each other using their container names as hostnames.