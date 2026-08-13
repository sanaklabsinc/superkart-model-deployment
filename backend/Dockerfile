FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy all files from the current directory to the container's working directory
COPY . .

# Install dependencies from the requirements file without using cache
RUN pip install --no-cache-dir --upgrade -r requirements.txt

# Start the Flask application using Gunicorn
# -w 4: Use 4 worker processes
# -b 0.0.0.0:7860: Bind to port 7860
# app:superkart_api: app.py contains the Flask instance named superkart_api
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:7860", "app:superkart_api"]