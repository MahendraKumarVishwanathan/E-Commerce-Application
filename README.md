# E-Commerce-Application
Excited to share my latest project: E-commerce Microservices Deployment using Docker Containers!

💡 Why Docker for E-Commerce?
🔹 Portability – Runs the same way across dev, test, and production
🔹 Scalability – Easily scale services with docker-compose or Kubernetes
🔹 Faster Deployment – Quick setup without dependency issues


Microservice bashed web applcation deployment using docker.
1> Containerized each micro service application.
2>Define a docker compose setup.

Docker compose: Is a tool that simplifies and manage multiple container docker application using yaml file.
Yaml file specify application network, Volume, services, images, Container name, ports.

Example:

We can Create Start all the service using a single command {docker compose up}

Define a complex applications in to consist of multiple docker container, Making is easier to define build and run them.

Docker compose provide command for managing the entier lifecycle of your application, including starting, Stopping, rebuilding, viewing status and streaming logs.

docker compose up – Builds, Create starts and attached to container for a service.
docker compose down – Stopped and remove container, Network and volume.
docker compose logs – stream logs output of the running container.
docker compose ps – List the container and their status
docker compose build – Build the images.

E-Commerce application has been spilited as micro service application as following environment.

      - profile-management
      - product-catalog
      - product-inventory
      - order-management
      - shipping-and-handling
      - contact-support-team

Every service’s deveoped using different languages.
