# Use the latest Ubuntu as the base image
FROM ubuntu:latest

# Update and upgrade APT packages
RUN apt-get update && apt-get upgrade -y

# Install Python3, pip3, and Flask
RUN apt-get install -y python3 python3-pip

# Remove EXTERNALLY-MANAGED file if needed
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Install Flask using pip3
RUN pip3 install flask

# Install flask-cors
RUN pip3 install flask-cors

# Set the working directory to /app
WORKDIR /app

# Copy the Flask app into the container
COPY api.py /app

# Make port 5252 available to the world outside this container
EXPOSE 5252

# Define environment variable
ENV FLASK_APP=api.py

# Set the command to run the Flask app
CMD ["python3", "api.py"]
