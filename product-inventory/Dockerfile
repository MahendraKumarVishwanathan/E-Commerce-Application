# Use the official Python image as the base image
FROM python:3.10-slim
# Set the working directory inside the container
WORKDIR /app
# Copy the requirements file to the working directory
COPY requirements.* /app
# Install the dependencies
RUN pip install --no-cache-dir -r requirements.txt
# Copy the rest of the application source code
COPY . /app
# Expose the port that the API listens on
EXPOSE 3002
# Run the Flask application when the container starts
CMD ["python3","inventory_api.py"]
