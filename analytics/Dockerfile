#Python image
FROM python:3.11

# Working directory
WORKDIR /app

# Copy the rest of the application code to the working directory
COPY  . /app

# Python dependencies
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Expose port 80
EXPOSE 80

# Command to run the application
CMD ["python", "app.py"]