# Order Management Microservice

This Docker image provides a Spring Boot application for managing user orders in an e-commerce platform. It allows adding products to a cart, calculating cart totals, and processing purchases.

## Usage

To run a container from this image, use the following command:

```bash
docker run --network my-network \
-e PRODUCT_INVENTORY_API_HOST=http://product-inventory \
-e PRODUCT_CATALOG_API_HOST=http://product-catalog \
-e SHIPPING_HANDLING_API_HOST=http://shipping-and-handling \
-p 9090:9090 --name order-management rslim087/order-management
```

The microservice will be accessible at `http://localhost:9090`.

### API Endpoints

- `POST /api/orders/{userId}/cart`: Adds a product to the user's cart.
- `GET /api/orders/{userId}/cart/subtotal`: Retrieves the cart subtotal for the user.
- `GET /api/orders/{userId}/cart/shipping`: Retrieves the shipping total for the user's cart.
- `GET /api/orders/{userId}/cart/total`: Retrieves the total cart value including shipping for the user.
- `POST /api/orders/{userId}/purchase`: Processes the purchase of the user's cart.
- `GET /api/orders/{userId}/cart`: Retrieves all items in the user's cart.

## Environment Variables

The container requires the following environment variables to be set:

- `PRODUCT_INVENTORY_API_HOST`: The URL of the product inventory microservice.
- `PRODUCT_CATALOG_API_HOST`: The URL of the product catalog microservice.
- `SHIPPING_HANDLING_API_HOST`: The URL of the shipping and handling microservice.

These variables are used by the application to communicate with the necessary microservices to fetch product details, inventory status, and shipping information.

## Docker Network

To ensure the Order Management microservice can communicate with the required microservices, it should be connected to the same Docker network. Here’s how you can set it up:

1. Create a Docker network if you haven't already:
   ```bash
   docker network create my-network
   ```

2. Run the Order Management microservice along with the other microservices on the same network, using the `--network` flag as shown in the usage example.