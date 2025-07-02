# Use the specified Python Alpine image as the base
FROM python:3.13.4-alpine3.22

# Set the working directory inside the container
WORKDIR /app

# Copy the dependencies file and install them
# This is done in a separate step to leverage Docker's layer caching.
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code into the container
COPY . .

# Expose the port the application will run on
EXPOSE 8000

# Specify the command to run the application using uvicorn
# --host 0.0.0.0 makes the server accessible from outside the container.
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000", "--reload"]

## criar a imagem
# docker build -t [nome da imagem] .

## rodar o container
# docker run -p 8000:8000 [nome da imagem]

## rodar o container com docker-compose
# docker-compose up -d
# docker-compose up 