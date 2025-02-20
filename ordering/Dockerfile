# Use an official Python image
FROM python:3.10

# Set the working directory
WORKDIR /main

# Copy the application files
COPY . /main

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose the port
EXPOSE 5001

# Run the application
CMD ["python", "main.py"]