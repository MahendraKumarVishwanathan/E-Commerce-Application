# Use the official Golang image as the base image
FROM python:3.8-slim
# Set the working directory inside the container
WORKDIR /app
# Copy the requirements file to the working directory
COPY requirements.txt /app
# Install the dependencies
RUN pip install -r requirements.txt
# Copy the Flask application to the working directory
COPY . /app
# Expose the port that the Flask application listens on
EXPOSE 8000
# Run the Flask application when the container starts
CMD ["python3", "server.py"]                        
