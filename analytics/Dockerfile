#Python image
FROM python:3.10-slim-buster

# Working directory
WORKDIR /app

# Copy the rest of the application code to the working directory
COPY  . /app

# Python dependencies
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Expose port 5153
EXPOSE 5153

# Command to run the application
CMD ["python", "app.py"]