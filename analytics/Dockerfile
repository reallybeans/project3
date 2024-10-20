#Python image
FROM python:3.10-slim

# Working directory
WORKDIR /app

# Copy the rest of the application code to the working directory
COPY  . /app

# Python dependencies
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Expose port 5153
EXPOSE 5153

# Environment variables
ENV DB_USERNAME=myuser
ENV DB_PASSWORD=mypassword
ENV DB_HOST=host.docker.internal
ENV DB_PORT=5433
ENV DB_NAME=mydatabase

# Command to run the application
CMD ["python", "app.py"]