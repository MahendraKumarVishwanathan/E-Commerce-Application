# Product Inventory Microservice

This Docker image provides a microservice for managing product inventory. It allows retrieving inventory for all products, fetching inventory for a single product by its ID, and reducing the quantity of a product when an order is placed.

## Usage

To run a container from this image, use the following command:

```bash
docker run -p 3002:3002 product-inventory-microservice
```

The microservice will be accessible at `http://localhost:3002`.

### API Endpoints

- `GET /api/inventory`: Retrieves inventory for all products.
- `GET /api/inventory/<product_id>`: Retrieves inventory for a single product by its ID.
- `POST /api/order/<product_id>`: Reduces the quantity of a product by 1 when an order is placed.

## Environment Variables

This microservice does not require any environment variables to be set.

## Volumes

This microservice does not use any volumes.

## Docker Network

To enable communication between the Product Inventory microservice and other microservices or applications, ensure that the containers are connected to the same Docker network. You can achieve this by following these steps:

1. Create a Docker network:
   ```bash
   docker network create my-network
   ```

2. Run the Product Inventory microservice container with the `--network` flag:
   ```bash
   docker run --network my-network -p 3002:3002 product-inventory-microservice
   ```

3. Run other microservice or application containers on the same network:
   ```bash
   docker run --network my-network -p 4000:4000 ecommerce-ui
   ```

By connecting the containers to the same Docker network, they can communicate with each other using their container names as hostnames.