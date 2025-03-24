# Shipping and Handling Microservice

This Docker image provides a microservice for calculating shipping fees based on product categories and time of day. It also provides a shipping explanation and returns all shipping fees for products.

## Usage

To run a container from this image, use the following command:

```bash
docker run -p 8080:8080 shipping-and-handling
```

The microservice will be accessible at `http://localhost:8080`.

### API Endpoints

- `GET /shipping-fee?product_id=<product_id>`: Calculates the shipping fee for a product based on its ID.
- `GET /shipping-explanation`: Provides a sophisticated explanation of the shipping fee calculation.
- `GET /all-shipping-fees`: Returns all shipping fees for products.

## Environment Variables

This microservice does not require any environment variables to be set.

## Volumes

This microservice does not use any volumes.

## Docker Network

To enable communication between the Shipping and Handling microservice and other microservices or applications, ensure that the containers are connected to the same Docker network. You can achieve this by following these steps:

1. Create a Docker network:
  ```bash
  docker network create my-network
  ```

2. Run the Shipping and Handling microservice container with the `--network` flag:
  ```bash
  docker run --network my-network -p 8080:8080 shipping-and-handling
  ```

3. Run other microservice or application containers on the same network:
  ```bash
  docker run --network my-network -p 4000:4000 ecommerce-ui
  ```

By connecting the containers to the same Docker network, they can communicate with each other using their container names as hostnames.